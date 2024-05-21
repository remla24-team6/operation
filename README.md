# remla24-team6
Operation repository for CS4295 Release Engineering for Machine Learning Applications (2023/24 Q4)

### Repositories

- operation: [operation](https://github.com/remla24-team6/operation)
- model training: [phishing-detection-cnn](https://github.com/remla24-team6/phishing_detection_cnn)
- model service: [model_service](https://github.com/remla24-team6/model-service)
- app: [app](https://github.com/remla24-team6/app)
- lib-version: [lib-version](https://github.com/remla24-team6/lib-version)
- ml-lib: [ml-lib](https://github.com/remla24-team6/ml-lib)

## Running via docker-compose:

1. Make sure that docker is installed.
2. Clone the repo
3. Navigate into the repo and run `docker-compose up`
4. Go to [http://0.0.0.0:8000/](http://0.0.0.0:8000/) and test the system.


## Running with Vagrant/Ansible/Kubernetes

Make sure you have cloned this repository.

### Vagrant

Make sure vagrant is installed along with an appropriate provider (e.g. VirtualBox).
To set up the nodes in the system, run:
```
vagrant up
```
Sometimes vagrant is a bit flaky and does not set up the nodes properly. If this is the case, run:
```
vagrant destroy <malfunctioning node>
vagrant up
```

The control node should be available on `192.168.60.2`. The worker nodes should be available on `192.168.61.2`, `192.168.61.3` ... etc. (If you configure more than 2 worker nodes)

### Ansible
TODO

### Kubernetes
TODO



## Running Kubernetes
1. Install minikube on your machine.
2. Start a local kubernetes cluster by running `minikube start --driver=docker`.
3. Emable ingress by running `minikube addons enable ingress`.
4. Run the application by running `kubectl apply -f kubernetes`.
5. Check if the pods and servies are up by running `kubectl get pods` and `kubectl get services`.
6. Create a tunnel using `minikube tunnel`
7. Now, run the app on `localhost`

## Comments 

### Comments for A1:
For this week's submission we implemented the following activities:
- Converted the notebook into Python scripts.
- Add dvc pipeline to train the model.
- Add dvc metrics to the code base.
- Installed static code formatting tool autopep8.
- Installed and configured two linters (pylint & flake8) to check code quality.
- Display pylint code quality information in output file.

### Comments for A2:
For this week's submission we implemented the following activities:
- Separated out the phishing pre-prcessing logic into a separate python package (ml-lib)
- Updated model training repository to use the pre-prcessing library. Added linters to github workflow.
- Created a new version-aware python library (lib-version) that can be imported in the app.
- Created a model-service that loads a trained model (which is stored in google drive) and exposes endpoints to predict using that model.
  This service uses the lib-ml python package for preprocessing. Implements Swagger for API documentation.
- Created a Django app that has both the app-frontend and the app-service (app)
  