pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'javac -d . src/*.java' // Compile Java code
            }
        }
        stage('Test') {
            steps {
                sh 'java -cp .:junit-platform-console-standalone-1.7.2.jar org.junit.platform.console.ConsoleLauncher --scan-class-path' // Run tests
            }
        }
        stage('Package') {
            steps {
                sh 'jar -cvf myapp.jar *' // Package application
            }
        }
    }
}