# remla24-team6
Operation repository for CS4295 Release Engineering for Machine Learning Applications (2023/24 Q4)

## Deployment

1. Make sure that docker is installed.
2. Clone the repo
3. Navigate into the repo and run `docker-compose up`
4. Go to [http://0.0.0.0:8000/](http://0.0.0.0:8000/) and test the system.

Note that due to time constraints, the model is not trained extensively. This means that the system will likely give some random-ish output.

### Repositories

- operation: [remla24-team6](https://github.com/Roodster/remla24-team6/)
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
