node {

 stage ('Checkout')  {



     build job: 'CheckOut'

 }

stage ('Build') {

     build job: 'Build'

    }

stage ('Code Quality scan') {

      build job: 'Code_Quality'

        }



stage('Archive Artifacts') {

build job: 'Archive_Artifacts'

}

 stage('Publish to Artifactory') {

build job: 'Publish_To_Artifactory'

}

stage ('DEV Approve')

      {

            echo "Taking approval from DEV"



            timeout(time: 7, unit: 'DAYS') {

            input message: 'Do you want to deploy?', submitter: 'admin'

            }

     }

stage ('DEV Deploy')

         {

             build job: 'Deploy_To_Container'

          }



stage ('Slack notification') {



build job: 'Slack_Notification'

    }



}