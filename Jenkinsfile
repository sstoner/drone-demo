podTemplate(containers: [
    containerTemplate(alwaysPullImage: false, 
                        args: 'ls -l ', 
                        command: '/bin/sh -c', 
                        envVars: [], 
                        image: 'golang-alpine', 
                        livenessProbe: containerLivenessProbe(execArgs: '', failureThreshold: 0, initialDelaySeconds: 0, periodSeconds: 0, successThreshold: 0, timeoutSeconds: 0), 
                        name: 'golang-backend', 
                        ports: [], 
                        privileged: false, 
                        resourceLimitCpu: '', 
                        resourceLimitMemory: '', 
                        resourceRequestCpu: '', 
                        resourceRequestMemory: '', 
                        shell: null, 
                        ttyEnabled: true, 
                        workingDir: '/home/jenkins')], 
            inheritFrom: '', 
            instanceCap: 0, 
            label: 'my-label', 
            name: 'ppk-cicd', 
            namespace: 'default', 
            nodeSelector: '', 
            podRetention: always(), 
            serviceAccount: '', 
            workspaceVolume: emptyDirWorkspaceVolume(false)) 
            {
                    stage('Run shell') {
                           container('golang-backend') {
                                sh 'go version'
                              }
                        }
}

