pipeline{
agent{
docker{
image 'maven:3-alpine'
args '-v "$HOME/.m2":/root/.m2'
}
}
stages{
 stage('maven-build'){
 steps{
 sh '''mvn -B -DskipTests clean package
 mvn package
 cd /home
 ls -a
 '''
 sh ' 
 sh 'curl http://localhost:8085/github-maven-example-0.1-SNAPSHOT-sources.jar'
}
}
}
}
