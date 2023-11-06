# Decisions for Building and Packaging Django in Docker with CI/CD



One of the components of this test involves establishing a continuous integration and continuous deployment (CI/CD) flow for the Django application hosted in this repository. I'll begin by explaining the decision to split the various pipelines.

In this context, I've chosen to create three distinct but interconnected pipelines for this application.


````
ci-django.yml
django-build-push.yml
docs-build-push.yml
````

### Description of ci-django.yml

I've opted to set up a continuous integration pipeline that enables you to run tests with each push or pull request made to the master branch. This approach allows you to maintain control over the changes made to your Django application, verifying their correctness if tests are available.

The necessary environment variables are provided to the application, as seen below:

````
env:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      DATABASE_URL: localhost # default host value for the database
      POSTGRES_DB: djtesting
      POSTGRES_PORT: 5432
      DJANGO_SECRET_KEY: ZjF1YRwsfquI5GkKiSnt5NJWTeNfFqMcJCarpOLXlZFVWTJAFLmEXf0DUmJ0BbjK
      CELERY_BROKER_URL: redis://redis:6379/0
      USE_DOCKER: no
      DB_HOST: localhost
`````

Here is an example of running these tests:

https://github.com/tomctm/devops-coding-challenge/actions/runs/6769076749/job/18394779922


### Description of django-build-push.yml


In the context of the pipeline for the build and push to Docker Hub, I've divided it into two segments.

On one hand, there's the application itself, and on the other hand, there's the creation of an image containing the documentation part.

For the application, we execute the build, tagging, and push stages.

Regarding tagging, we've chosen to derive the branch name while respecting the team's utilization of a semantic versioning system, enabling branch names that align with the various releases.


### Description of docs-build-push.yml


Upon reviewing the code within the local.yml file and examining the application code, it becomes evident that the application relies on PostgreSQL, Redis, and Mailhog. As these are third-party applications, we recommend deploying them using their updated and community-maintained images.

As a final step, for the documentation component, we've established the build, tagging, and push stages to Docker Hub.

### Optional Actions

Should we consider enhancing these pipelines, our focus would shift towards the security aspect. We would implement a phase where external tools such as Snyk or Sonar are employed for code analysis of these images.