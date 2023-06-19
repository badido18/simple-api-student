#  Part 1 : Docker

### Why do we need a multistage build?
- A multistage build is necessary in order to optimize the size and efficiency of Docker images. By breaking down the build process into multiple stages, we can separate the build environment from the runtime environment, reducing the final image size and eliminating unnecessary dependencies.
### This is how to publish
```bash
docker login
docker image push <USERNAME>/database:<version or tag>
docker image push <USERNAME>/backend:<version or tag>
docker image push <USERNAME>/httpd:<version or tag>
```

#  Partie 2 : Github Actions

### What are testcontainers?
- In the context of GitHub Actions, testcontainers are a valuable tool for running tests that require external dependencies, such as databases or message brokers, in isolated and reproducible environments. Testcontainers provide lightweight, disposable containers that can be spun up and torn down programmatically, allowing developers to easily set up and tear down these dependencies during the testing process. This helps ensure consistent and reliable test results, as well as simplifying the configuration and management of test environments.


#### This project's Github Action configuration
- There is 2 main pipelines
    - **First** builds and pushes the images that don't require test to **Docker Hub** 
    - **Second** launchs backend test , and then **if and only if** the tests are successfull, it will build and push the backend image to **Docker Hub**

#  Partie 3 : Ansible

To execute the ansible tasks

```bash
cd ansible
ansible-playbook -i inventories/setup.yml playbook.yml
```




