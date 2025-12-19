node {

    stage('Checkout') {
        git branch: 'main',
            url: 'https://github.com/sairohithtadangi7-coder/pet_shop.git'
    }

    stage('Build') {
        sh 'mvn clean install'
    }

    stage('sonarqube Analysis') {
        withSonarQubeEnv('sonarqube') {
            sh 'mvn sonar:sonar'
        }
    }

}
