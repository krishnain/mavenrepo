@Library('library')_
pipeline
{
    agent any
    stages
    {
       stage('ContDownload')
        {
            steps
            {
                script
                {
                    cicd.newGit("maven")
                }
            }
            
        }
        stage('ContBuild')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        stage('ContDeployment')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("SharedLibrary1","172.31.0.175","testapp")
                }
            }
        }
        stage('ContTesting')
        {
            steps
            {
                script
                {
                   cicd.newGit("FunctionalTesting")
                   cicd.runSelenium("SharedLibrary1")
                }
                
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                script
                {
                    cicd.newDeploy(env.WORKSPACE,"172.31.15.186","prodapp")
                }
            }
        }
        
        
        
        
        
        
        
        
        
        
        
        
    }
}
