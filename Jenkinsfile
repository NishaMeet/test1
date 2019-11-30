pipeline {
  agent any
  
  parameters {
		string(defaultValue: "", description: 'Enter Text here', name: 'text')
		booleanParam(defaultValue: false, description: 'testing', name: 'test')
	}
	
  node(){
	stage ('test1 - Build') {
	   steps {
	   conditionalSteps { 
	        condition {
	            booleanCondition('${ENV,var="test"}')
	        }
	        steps{
		build job: 'test2 - Build', parameters: [
        string(name: 'text', value: env.NAME)
    ], wait: false
	}
  }
}
  node(){
	stage ('test2 - Build') {
	steps {
		sh """ 
		echo $test 
		"""
	}
  }
}
}
}
