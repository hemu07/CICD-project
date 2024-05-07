# CICD-project
Jenkins Pipeline for Java-based application using Maven, SonarQube, Argo CD, Helm and Kubernetes


![image](https://github.com/hemu07/CICD-project/assets/90203539/bebf6e54-50d8-4caa-88f8-ca79ba94b968)

- building the app locally
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/425f3862-b767-4b6e-acb0-01bea94aec8f)
- running the application
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/37b7b87b-2d6a-4b78-a861-102f6c525c3f)
- accessing the app locally
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/e70d3ef0-db53-43fc-9025-e4a7083054e5)

- spin up t2.large ec2 instance in AWS
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/07d41b16-9525-4866-bbcd-61b64669a924)

- ssh into the instance
- install java 11
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/9ad917f6-17b9-41f8-b525-6ca6b4758a58)
- install jenkins on the instance
- setup jenkins admin user
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/dc9935f6-cdb1-48c4-8fb3-ee23673312d0)
  18e66e052b6347f180e6c7f50117ce39

  - configure maven plugin, install docker pipeline plugin and sonar scanner plugin and restart the jenkins
  - install sonarqube in the ec2 instance
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/2c2fc6c9-9b56-40f5-a5e0-f1af56fd30b9)
  - Docker Slave Configuration
  - install docker and give jenkins and ubuntu access to docker daemon
  - ![image](https://github.com/hemu07/CICD-project/assets/90203539/93af5b54-973c-4767-90c4-f6fb4ec881b6)

- create jenkins pipeline (from SCM)
  
