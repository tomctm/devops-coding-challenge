# TO-DO


- As mentioned, I would focus on establishing security checks within the pipeline against external layers that provide code information (Sonar, Snyk, etc.).
- I couldn't find any tests within the application to verify its functionality.
- I would try to establish default requirements for both local testing and production deployment of the application since separating versions and libraries in different environments can lead to post-deployment issues.
- I would have Vault installed for managing secrets within the application and injecting them during the deployment phase.