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
      		bat "dotnet restore C:\\Users\\karla\\TEST_project\\kontent-sample-app-net\\DancingGoat\\DancingGoat.csproj"
     	    }
  	}

	stage('Clean'){
    	    steps{
        	bat "dotnet clean C:\\Users\\karla\\TEST_project\\kontent-sample-app-net\\DancingGoat\\DancingGoat.csproj"
     	    }
   	}

	stage('Build'){
   	    steps{
      		bat "dotnet build C:\\Users\\karla\\TEST_project\\kontent-sample-app-net\\DancingGoat\\DancingGoat.csproj --configuration Release"
    	    }
	}
	    
	    
	stage('Test: Unit Test'){
   	    steps {
     		bat "dotnet test C:\\Users\\karla\\TEST_project\\kontent-sample-app-net\\DancingGoat.Tests\\DancingGoat.Tests.csproj"
     	    }
  	}
       
 	stage('Test: Integration Test'){
    	    steps {
       		bat "dotnet test C:\\Users\\karla\\TEST_project\\kontent-sample-app-net\\DancingGoat.Tests\\DancingGoat.Tests.csproj"
      	    }
   	}
    }
 }
