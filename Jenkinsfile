pipeline{
agent any
stages{
stage("1st step: checkout the code from github"){
steps{
    git credentialsId: 'ddf036b3-efcb-4cfc-90fd-8803364d1f70', url: 'https://github.com/heerakrishna/addressbook-cicd-project'

}
}
stage("2nd stage: compile the code"){
steps{
sh "mvn compile"
}
}
stage("3rd stage: testing the code"){
steps{
sh "mvn test"
}
}
stage("4th stage: quality assurance of the code"){
steps{
sh "mvn checkstyle:checkstyle"
}
}
stage("5th stage: package the project"){
steps{
sh "mvn package"
}
}
stage("6 stage: deploy the project" ){
steps{
sh 'sudo cp "/var/lib/jenkins/workspace/my project@2/target/addressbook.war" /home/ubuntu/apache-tomcat-9.0.111/webapps/'
}
}
}
}
