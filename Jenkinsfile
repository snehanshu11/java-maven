pipeline {
    agent any
    
    parameters {
        string("name":"branch", "defaultValue":"main", "description":"branch to build")
    }

    stages {
        stage("Code Checkout") {
            steps {
                sh "git clone -b ${params.branch} https://github.com/snehanshu11/java-maven.git"
                dir('java-maven') {
                    sh "git checkout ${params.branch}"
                }
            }
        }
        
        stage("Code Build") {
            when {
                expression {
                    params.branch == "main" || params.branch == "main"
                }
            }
            steps {
                dir('java-maven') {
                    sh '/Users/snehanshu.suman/Downloads/apache-maven-3.8.6/bin/mvn clean deploy'
                }
            }
        }
    }
}