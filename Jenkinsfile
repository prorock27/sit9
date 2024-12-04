pipeline {
    agent any

    environment {
        ANT_HOME = 'C:\\buildTool\\apache-ant-1.10.15'   // Путь к Apache Ant
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-21'    // Путь к JDK
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/prorock27/sit9.git' // Укажите ваш репозиторий
            }
        }

        stage('Build') {
            steps {
                script {
                    // Выполнение сборки с использованием Apache Ant
                    bat '"${ANT_HOME}\\bin\\ant" -f "D:\\LABS\\Лабы\\Ситаири\\sit9\\build.xml" build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Выполнение тестов с использованием Apache Ant
                    bat '"${ANT_HOME}\\bin\\ant" -f "D:\\LABS\\Лабы\\Ситаири\\sit9\\build.xml" test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Деплой (если необходимо, настройте это)
                }
            }
        }
    }

    post {
        success {
            echo 'Build and tests successful'
        }
        failure {
            echo 'Build or tests failed'
        }
    }
}
