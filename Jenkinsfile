pipeline {

    agent any
	environment { server_cred=credentials('servercred')}
    {
        stage ("Build") { 
            steps
            {
                echo 'Building the application1'
				echo $server_cred
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
