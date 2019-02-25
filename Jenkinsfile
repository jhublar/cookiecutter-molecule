
pipeline {
    agent {
        label 'linux'
    }
    options {
        disableConcurrentBuilds()
    }
    stages {
        stage('ansible.role.ci') {
            steps {
                build job: 'administration/ansible.role.ci', parameters: [
                    string(name: 'role', value: scm.userRemoteConfigs[0].url),
                    string(name: 'branch', value: BRANCH_NAME)
                ]
            }
        }
    }
}