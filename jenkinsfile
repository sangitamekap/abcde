node(){
    stage('Print data')
    {
        sh 'whoami'
        echo "Hi Working fine"
        echo "current branch is ${env.BRANCH_NAME}"
    }
    
    stage('Print data')
    {
     checkout scm
    }
    
    stage('setup enveronment'){
            if(env.BRANCH_NAME=='master')
            {
               sh 'ansible-playbook -i ./prod.inventory ./docker.yml'
            } 
            if(env.BRANCH_NAME=='Dev')
            {
               sh 'ansible-playbook -i ./dev.inventory ./docker.yml'
            }
            if(env.BRANCH_NAME=='Stage')
            {
               sh 'ansible-playbook -i ./qa.inventory ./docker.yml'
            }
        } 
}
