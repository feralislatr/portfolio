#!groovy

node {
        currentBuild.result = "SUCCESS"
        
        try {
                stage "Prepare environment"
                  //sh 'env | sort'
                  checkout scm
                  //sh ('sudo usermod -aG docker jenkins && groups')
                  
                  sh "echo $env.BRANCH_NAME | tr '[:upper:]' '[:lower:]' > branchnamefile"
                  def branchName=readFile('branchnamefile').trim()
                  sh "echo $branchName"
                  
                stage "Print Variables"
                   sh "pwd"
                   sh('cat /var/lib/jenkins/workspace/params.properties > COMMENT')
                   def comment = readFile('COMMENT').trim()
                   sh "echo $comment"

        } catch (err) {
            throw err
        }
}
