// Powered by Infostretch 
timestamps {

node () {

	stage ('test1 - Build') {
	parameters {
		string(defaultValue: "", description: 'Enter Text here', name: 'text')
		booleanParam(defaultValue: false, description: 'testing', name: 'test')
	}
		steps {
        conditionalSteps {
            condition {
                booleanCondition('${$Java}')
            }
            runner('Run')
            steps {
				 build job: 'test2 - Build', parameters: [ string(name: 'text', value: env.NAME) ], wait: false
            }
        }
    }
 	
// Unable to convert a build step referring to "org.jenkinsci.plugins.conditionalbuildstep.singlestep.SingleConditionalBuilder". Please verify and convert manually if required. 
	}
	stage ('test2 - Build') {
 			// Shell build step
sh """ 
echo $test 
 """ 
	}
}
}
