def gv

pipeline {

    agent any
	environment 
		{ 
		server_cred=credentials('servercred')
		}
	stages
    {
		stage ("init") { 
            steps
            {
                script 
				{
				gv= load "script.groovy"
				}
            }

		}
        stage ("Build") { 
            steps
            {
                script 
				{
				gv.buildApp()
				}
				
				withCredentials([usernamePassword(credentialsId: 'servercred', passwordVariable: 'passw', usernameVariable: 'user')])
				{
						echo "${user}"
						echo "${passw}"
						}
            }

         }

        stage ("Test"){ 

            steps
            {
                script 
				{
				gv.testApp()
				}
            }

        }

        stage ("deploy"){

            steps
             {
               script 
				{
				gv.deployApp()
				} 
             }

    }

    }

}
