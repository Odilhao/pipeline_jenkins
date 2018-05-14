node {
   def mvnHome
   stage('Preparation') {
      git 'https://github.com/Odilhao/os-sample-java-web.git'
      mvnHome = tool 'M3'
   }
   stage('Build') {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
           archive 'target/*.jar'
}
