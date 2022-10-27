This project also uses CircleCi to create a pipeline that automates the deployment process.
![CircleCi](https://img.shields.io/badge/Main-Live-brightgreen)

### Pipeline process

CircleCi is connected to both the github repository and AWS using the AWS Key ID. CircleCi then watches for any pushed changes that were made and starts a workflow which consists of two jobs:

- Building
- Deploying

#### Building

During the building job, node js is installed using the node js orb and and all dependancies are installed using the `npm install` command for both the front-end and back-end.

After that the command `npm run build` is ran for both the front-end and back-end to create the build folders.

#### Deploying

During the deploying phase, AWS CLI and Elastic Beanstalk CLI are installed AWS is configured using the Access Key ID.

After that the apps are deployed using `npm run deploy`.