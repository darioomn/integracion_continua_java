#!groovy


stage name: 'setup'
node {
    wrap([$class: 'Groovy']) {
        def script = '''
        println "\n\nSystem Properties"
        System.properties.each { k,v -> println "$k = $v" }

        println "\n\nEnvironment"
        System.getenv().each { k,v -> println "$k = $v" }
'''
    }

    // Testing
	sh 'pwd'
	sh 'ls -la'
    git url: 'https://github.com/loverde/jenkinsfile-test'
}

stage name: 'build'
node {
	sh 'pwd'
	sh 'ls -la'
	sh './gradlew clean build'
}

stage name: 'postbuild'
node {
	sh 'pwd'
	sh 'ls -la'
}
