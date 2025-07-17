// global variables
// persistant
// Used in the groovy script

pipeline{
    agent any
    //environment{// variables to be passed to sh. creds/paths}
    /*options{
        timestamps() //global
        disableConcurrentBuilds() //global
        timeout(time: 10, unit: "Minutes")
        retry(5) //stage
    */
    }
    // tools{}
    stages{
        stage("Make a dir"){
            //catchError(buildrResult: "UNSTABLE", stageResult: "UNSTABLE")
            options{timeout(time: 1, units: "Minutes")}
            steps{
                //script{"1""2"} // better way at handling blocks of steps if things get too long or complicated. Has to be sh or bash script.                
                sh "mkdir ~/jenkins || true" // pipe pipe because if it can't mkdir it likely already exists so the error is also true. Don't always use this concept.
                //sh "cd ~/jenkins"
                //sh "touch file.txt" // won't write into the folder above, individual shells.

            }
            }
        
        stage("add a file"){
            steps{
                sh "touch ~/jenkins/file.txt"
            }
            post{
                success {echo "successfully ran stages!"}
                failure {echo "we failed..."}
                always {echo "We can always try again."}
                /*archivetheartifacts{}
                email
                clean up actions
                printing file systems
                */
                }    
        }
    }
}