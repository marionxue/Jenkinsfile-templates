# Jenkinsfile-templates
Some templates of Jenkinsfile for know jenkins more.

## jenkins
- [x] install jenkins with docker
- [x] install jenkins with kubernetes

## Jenkinsfile
- [x] [declarative pipeline](./declarative_pipeline_template.Jenkinsfile)
- [x] [script pipeline](./script_pipeline_template.Jenkinsfile)
- [x] use retry and timeout to control jenkins pipeline.
  - [x] [if health-check is failed,  continue to execute deploy to retry(3)](./declarative_retry_timeout-1.Jenkinsfile)
  - [x] [if deploy has not finished in timout time. tag this job is failed.](./declarative_retry_timeout-2.Jenkinsfile)
