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
- 
- setup jenkins admin user
  ![image](https://github.com/hemu07/CICD-project/assets/90203539/dc9935f6-cdb1-48c4-8fb3-ee23673312d0)
  18e66e052b6347f180e6c7f50117ce39

  - configure maven plugin, install docker pipeline plugin and sonar scanner plugin and restart the jenkins
  - install sonarqube in the ec2 instance
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/2c2fc6c9-9b56-40f5-a5e0-f1af56fd30b9)
  - Docker Slave Configuration
  - install docker and give jenkins and ubuntu access to docker daemon
  - ![image](https://github.com/hemu07/CICD-project/assets/90203539/93af5b54-973c-4767-90c4-f6fb4ec881b6)
 
  - access sonarqube on port 9000 (admin:admin) is the default username & password
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/a780d9f3-ea7d-4d13-95ff-86004f0bc8aa)

  - configure jenkins to use sonarqube
    - go to Myaccount --> security --> generate token -- copy it
      ![image](https://github.com/hemu07/CICD-project/assets/90203539/6e518fe2-3e31-43d2-92f9-c21790dd08eb)

    - add the token in credentials of jenkins
   
    - open kubernetes on docker desktop locally -- install argocd controller from operator hub - "https://operatorhub.io/operator/argocd-operator"
    - ![image](https://github.com/hemu07/CICD-project/assets/90203539/a634b471-37a9-4997-8763-6736fd9ed4b7)

    - start the controller
      ![image](https://github.com/hemu07/CICD-project/assets/90203539/27913ec3-a484-45ef-9109-a1ad37dd4df6)

  - now configure all the CI steps in jenkinsfile
  - create jenkins pipeline (from SCM)
  - build the CI pipeline & image should be pushed to docker hub repo
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/c9d45099-367e-4f3e-b7f8-3a3abce0c46d)
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/61408869-adc5-4cb5-b7ae-42d489f14599)
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/c7cea1f3-8103-4dfa-81a2-675220572bdc)

  - setup argocd controller
  - check whether all pods are in running stage now from previous argocd installation
  - install minikube as per OS (docker desktop or any other virtualisation platform is prerequisite)
  - start minikube

  - FROM OFFICAL docs of argocd copy basic file and apply
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/4c0e24e9-be60-470e-b2e9-9a3eab27e523)
  - edit svc to NodePort from ClusterPOrt to access argoCD from our browser
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/a3791eee-a827-4a59-9978-2388e0595f9a)

    ![image](https://github.com/hemu07/CICD-project/assets/90203539/c28fc31e-889a-4b20-b9c1-fce94e212af7)
  - open the ip in your browser
    -default username is admin, password is base64 encoded by k8s at `kubernetes get secret`
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/d48a78a1-2b7b-483c-9f9c-98d50687ba10)
    ![image](https://github.com/hemu07/CICD-project/assets/90203539/aef46be1-d5a2-4db1-8be1-16d1f5817845)

  
