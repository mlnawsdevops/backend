pipeline{
    agent{
        label 'AGENT-1'
    }

    options{
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    environment{
        appVersion = '' // this will become global, we can use across pipeline
    }

    stages{
        stage('read the version'){
            steps{
                script{
                // defining variable
                def packageJson = readJSON file: 'package.json' // web= pipeline utility steps --> readjson
                appVersion = packageJson.version // dynamically fetch the version from package.json
                echo "App version: ${appVersion}" // 1.0.0 
                }
            }
        }
    }
}