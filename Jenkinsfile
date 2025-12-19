node {

    stage('Checkout') {
        git branch: 'main',
            url: 'https://github.com/sairohithtadangi7-coder/pet_shop.git'
    }

    stage('Build') {
        sh 'mvn clean install'
    }

    stage('SonarQube Analysis') {
        withSonarQubeEnv('SonarQube') {
            sh '''
            mvn sonar:sonar \
            -Dsonar.projectKey=pet-shop \
            -Dsonar.projectName=pet-shop
            '''
        }
    }

}
