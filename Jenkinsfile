node {
   def mvnHome
   stage('Definindo o fonte') {
      git 'https://github.com/Odilhao/os-sample-java-web.git'
      mvnHome = tool 'mvn'
   }
   stage('Construindo') {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Resultado') {
           archive 'target/*.war'
}
}
