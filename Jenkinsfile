pipeline{
    agent any
    
    environment {
        dotnet ='C:\\Program Files (x86)\\dotnet\\'
        }
        
    stages{
 	stage('Checkout') {
    	    steps {
     		git credentialsId: 'github_login', url: 'https://github.com/karlardz2707/kontent-sample-app-net'
     	    }
  	}
	
	stage('Restore packages'){
   	    steps{
      		bat "dotnet restore YourProjectPath\\Your_Project.csproj"
     	    }
  	}

	stage('Clean'){
    	    steps{
        	bat "dotnet clean YourProjectPath\\Your_Project.csproj"
     	    }
   	}

	stage('Build'){
   	    steps{
      		bat "dotnet build YourProjectPath\\Your_Project.csproj --configuration Release"
    	    }
	}

	stage('Test: Unit Test'){
   	    steps {
     		bat "dotnet test YourProjectPath\\UnitTest_Project.csproj"
     	    }
  	}
       
 	stage('Test: Integration Test'){
    	    steps {
       		bat "dotnet test ProjectPath\\IntegrateTest_Project.csproj"
      	    }
   	}

	stage('Publish'){
     	    steps{
       		bat "dotnet publish YourProjectPath\\Your_Project.csproj "
       	    }
	}
    }
 }
