# remla24-team6
Operation repository for CS4295 Release Engineering for Machine Learning Applications (2023/24 Q4)

## Deployment

1. Make sure that docker is installed.
2. Clone the repo
3. Navigate into the repo and run `docker-compose up`
4. Go to [http://0.0.0.0:8000/](http://0.0.0.0:8000/) and test the system.


### Repositories

- operation: [operation](https://github.com/Roodster/remla24-team6/)
- model training: [phishing-detection-cnn](https://github.com/remla24-team6/phishing_detection_cnn)
- model service: [model_service](https://github.com/remla24-team6/model-service)
- app: [app](https://github.com/remla24-team6/app)
- lib-version: [lib-version](https://github.com/remla24-team6/lib-version)
- ml-lib: [ml-lib](https://github.com/remla24-team6/ml-lib)

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
  
