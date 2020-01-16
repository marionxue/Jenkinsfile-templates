pipeline {
    agent any
    stages {
        stage('CheckScm') {
            steps {
                sh 'echo "pull code from remote repository."'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Starting Build source code to docker images..."'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                sleep(2)
            }
        }
        stage('CheckDeployBeforce') {
            steps {
                sh 'echo "DeployQA"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('DeployQA') {
            steps {

                retry(3) {
                    sh 'curl -I https://google.com'
                    sh 'touch success'
                }
                // 1分钟后进行健康状态检查,如果不存在该文件,判定部署服务不正常,因此限制最多执行三次部署,三次部署如果还没有通过,判定部署失败
                timeout(time:1, unit: 'MINUTES') {
                    sh '''
                        ls -al
                        if [ -f "./success" ];then
                            echo "Delpoy done and success"
                            exit 0
                        fi
                    '''
                }
            }
        }
        stage('CheckDeployAfter') {
            steps {
                sh 'echo "check the service health status running in QA"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''

            }
        }
        stage('DeployProd') {
            steps {
                sh 'echo "Deploy Service to Prod"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}