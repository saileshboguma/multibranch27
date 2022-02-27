node('master')
{
    stage('Continuous Download_loans') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
    stage('Continuous Build-loans') 
	{
    sh label: '', script: 'mvn package'
	}
}
