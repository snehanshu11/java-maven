pipeline {
    agent any
    
    parameters {
        string("name":"branch", "defaultValue":"main", "description":"branch to build")
    }

    stages {
        stage("checkout") {
            steps {
                sh "git clone -b ${params.branch} https://github.com/snehanshu11/java-maven.git"
                dir('java-maven') {
                    sh "git checkout ${params.branch}"
                }
            }
        }
        
        stage("build - Main Branch") {
            when {
                expression {
                    params.branch == "main"
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