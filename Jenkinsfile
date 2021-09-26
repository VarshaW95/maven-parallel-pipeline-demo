pipeline
{
    agent any
    stages
    {
        stage('SCM Checkout')
        {steps { git branch: 'master', url: 'https://github.com/VarshaW95/maven-parallel-pipeline-demo.git'}}
    
    
        stage('Execute test cases and Build code')
        {
            parallel
            {  
                stage('Execute Test Cases')
                {
                steps
                {
                    withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {sh 'mvn test'}
                }
                }

                stage('Code Build')
                {
                steps
                { 
                    withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {sh 'mvn package'}
                }
                }       
            }
        }
    }


}