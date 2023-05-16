pipeline {

    agent any
	environment 
		{ 
		server_cred=credentials('servercred')
		}
	stages
    {
        stage ("Build") { 
            steps
            {
                echo 'Building the application1'
				withCredentials([usernamePassword(credentialsId: 'servercred', passwordVariable: 'passw', usernameVariable: 'user')])
				{
						echo $user
						echo $passw
						}
            }

         }

        stage ("Test"){ 

            steps
            {
                echo 'Testing the application1'
            }

        }

        stage ("deploy"){

            steps
             {
                echo 'Deploying the application'
             }

    }

    }

}
