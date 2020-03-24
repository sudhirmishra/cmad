ne {
agent any
tools{
maven 'Maven 3.6.1'
}
stages{
stage("build"){
steps{
echo 'Compiling users app..'
dir('java/cmad-ms-users'){
sh 'mvn compile'
}
}
}
stage("test"){
steps{
echo 'Running Unit Tets on users app..'
dir('java/cmad-ms-users'){
sh 'mvn clean test'
}
}
}
stage("package"){
steps{
echo 'Packaging users app'
dir('java/cmad-ms-users'){sh 'mvn package -DskipTests'
archiveArtifacts artifacts: 'java/cmad-ms-users/target/*.jar',
fingerprint: true
}
}
}
}
post{
always{
echo 'Building multibranch pipeline for users is completed..'
}
}
}
