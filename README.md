# DevOps Interview Test: Design a CI/CD Pipeline for a Django Repository

### Introduction

In this test, you are required to design a CI/CD pipeline for a Django repository using GitLab CI. You will have complete freedom to decide which stages, jobs, and scripts to include in the pipeline, based on your preferences and best practices for CI/CD.

For context, let’s imagine that the Django Team has started working on a project for a client and that they need a pipeline to confidently show their progress to both the Project Manager and the client itself.

Your task is to fork the provided Django repository, create the CI/CD pipeline, and then create a merge request back to the original repository.

The test is vague on purpose, we want you to design the pipeline based on what you think that should happen from start to finish.

Feel free to include integrations with any third party software that you think it would be useful.

### Prerequisites

- A Github account
- Familiarity with GitLab CI/CD / Github Actions
- Familiarity with Django
- Basic understanding of Docker

### Instructions
1. Fork the Django repository
    
    The first step is to fork the provided Django repository. You can find the repository at:
    
    ```
    <https://gitlab.com/mrmilu/devops/devops_interview_test>
    
    ```
    
    Click the "Fork" button in the top right corner and choose your personal namespace to create a fork.
    
2. Design the GitLab CI/CD pipelines
    
    Create a new file called `.gitlab-ci.yml` in the root of the Django project. This file will contain the GitLab CI configuration.
    
    Design the CI/CD pipeline according to your preferences and best practices. 
    
    We love containers, an image should be built.
    
    You may also include any other stages, jobs, or scripts that you consider important.
    
3. Commit and push your changes
4. Create a merge request
    
    Go to your forked repository on GitLab and create a new merge request:
    
    - Set the target branch to `master` in the original repository
    - Provide a descriptive title and any additional details in the description
    
    Click "Submit merge request" to initiate the review process.

### Optional: Deployment Suggestions

As an optional step, you can include a brief description of how and where you would deploy the Django application. Some examples of deployment options include cloud platforms like AWS, Google Cloud Platform, or Microsoft Azure, as well as on-premises or self-hosted environments.

Feel free to describe any specific services, configurations, or best practices you would use for deploying the Django application.

### Deliverables

- A forked Django repository with a `.gitlab-ci.yml` file containing your designed GitLab CI/CD pipeline or github-actions workflow
- Access granted to `iker.blanco@mrmilu.com` to the repo.
- A markdown file named `DECISIONS.md` with an outline of your decisions so we can know why you did (or didn’t) do what you did :)
- A markdown file named  `TODO.md` with an outline of the things that you would implement, fix, upgrade if you had more time.
- (Optional) A brief description of your preferred deployment strategy for the Django application

### Questions

If you have any questions, feel free to email us at devops+interviews@mrmilu.com


Good luck! We're looking forward to reviewing your work.
