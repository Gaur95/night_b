# night_b
## jenkinsfile for clone build run push
```
pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                git branch: 'docker', url: 'https://github.com/Gaur95/night_b.git'
            }
        }
        stage('build'){
            steps{
                sh 'docker build -t aakashgaur57/mycode:v${BUILD_NUMBER} .'
            }
        }
        stage('run'){
            steps{
                sh 'docker rm -f ak '
                sh 'docker run -itd --name ak -p 1144:80 aakashgaur57/mycode:v${BUILD_NUMBER}  '
            }
        }
        stage('push'){
            steps{
                sh 'docker push aakashgaur57/mycode:v${BUILD_NUMBER} '
            }
        }
    }
}
```
