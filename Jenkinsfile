def stack_name= "Mayank"
node {
   stage('stack_name') { 
   sh """
   ${JENKINS_HOME}/stacked_deployment/createenv.sh $stack_name
   ${JENKINS_HOME}/stacked_deployment/getdetailsenv.sh $stack_name
    """
   }
   stage ('remote_task'){
    getdetails = readFile '.resource'
    sh """
    ip=`echo ${getdetails}`
    sleep 30
    ${JENKINS_HOME}/stacked_deployment/remotetask.sh \${ip}
    """
   }
   
}
