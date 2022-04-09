/* groovylint-disable CompileStatic, DuplicateMapLiteral, DuplicateNumberLiteral, DuplicateStringLiteral, LineLength, NestedBlockDepth */
pipeline {
  agent none
  options {
    timeout(time: 60, unit: 'MINUTES')
  }
  stages {
    stage('Build') {
      agent {
        // https://plugins.jenkins.io/kubernetes/
        kubernetes {
          yaml '''
            spec:
              containers:
              - name: nginx
                image: nginx:latest
            '''
        }
      }
      options {
        timeout(time: 10, unit: 'MINUTES')
      }
      steps {
        container(name: 'nginx', shell: '/bin/bash') {
          sh('uname -a')
        }
      }
    }
    stage('Test') {
      agent {
        // https://plugins.jenkins.io/kubernetes/
        kubernetes {
          yaml '''
            spec:
              containers:
              - name: nginx
                image: nginx:latest
            '''
        }
      }
      options {
        timeout(time: 10, unit: 'MINUTES')
      }
      steps {
        container(name: 'nginx', shell: '/bin/bash') {
          sh('uname -a')
        }
      }
    }
    stage('Release') {
      agent {
        // https://plugins.jenkins.io/kubernetes/
        kubernetes {
          yaml '''
            spec:
              containers:
              - name: nginx
                image: nginx:latest
            '''
        }
      }
      options {
        timeout(time: 10, unit: 'MINUTES')
      }
      steps {
        container(name: 'nginx', shell: '/bin/bash') {
          sh('uname -a')
        }
      }
    }
    stage('Deploy (Development)') {
      agent {
        // https://plugins.jenkins.io/kubernetes/
        kubernetes {
          yaml '''
            spec:
              containers:
              - name: nginx
                image: nginx:latest
            '''
        }
      }
      options {
        timeout(time: 10, unit: 'MINUTES')
      }
      steps {
        container(name: 'nginx', shell: '/bin/bash') {
          sh('uname -a')
        }
      }
    }
    stage('Approve (for Production)') {
      agent none
      options {
        timeout(time: 5, unit: 'MINUTES')
      }
      steps {
        input(message: 'Approved?', ok: 'Yes')
      }
    }
    stage('Deploy (Production)') {
      agent {
        // https://plugins.jenkins.io/kubernetes/
        kubernetes {
          yaml '''
            spec:
              containers:
              - name: nginx
                image: nginx:latest
            '''
        }
      }
      options {
        timeout(time: 10, unit: 'MINUTES')
      }
      steps {
        container(name: 'nginx', shell: '/bin/bash') {
          sh('uname -a')
        }
      }
    }
  }
}
