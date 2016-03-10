#!groovy

/*
// standardBuild from: https://gist.github.com/jglick/b13b509bc236566c8829
def standardBuild(body) {
    def config = [:]
    body.resolveStrategy = Closure.DELEGATE_FIRST
    body.delegate = config
    body()
    stage 'checkout'
    node {
        checkout scm
        stage 'main'
        docker.image(config.environment).inside {
            sh config.mainScript
        }
        stage 'post'
        sh config.postScript
    }
}

standardBuild {
    environment = 'golang:1.5.0'
    mainScript = '''
go version
go build -v hello-world.go
'''
    postScript = '''
ls -l
./hello-world
'''
}
*/

node {
    stage 'checkout'
    checkout scm

    stage 'build'
    if (isUnix()) {
        echo "unix mode"
	    sh 'pwd'
        sh "ls -la"
        sh './gradlew clean build'
    } else {
        echo "windows mode"
        bat "pwd"
        bat "dir"
        bat './gradlew.bat clean build'
    }

    stage: 'postbuild'
    if (isUnix()) {
        sh 'ls -la'
    } else { 
        bat 'dir'
    }
}
