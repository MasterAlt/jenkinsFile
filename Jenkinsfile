node{
	stage('Checkout'){
		cleanWs()

		// Method 1: Create directories and use them to clone individual modules but this requires admin level permissions and is not secured
		echo "Creating Directories for X Project"

		// Give all the repo names in place of one, two, three
        new File('one').mkdir()
        new File('two').mkdir()
        new File('three').mkdir()

		// clone each repo make sure you change the branch and repo here and the folder name which you created above,
    	dir ('one') {
    	    git branch: "release-2.10.0", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-devops.git'
    	}

    	dir ('two') {
    	    git branch: "release-2.7.0", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-data-pipeline.git'
    	}
    	dir ('three') {
    	    git branch: "master", changelog: false, poll: false, url: 'https://github.com/smyaltamash/king.git'
    	}
		
		// Method 2: Use checkout module to clone into specific folder and branch also use the private repo authentication
		//checkout([$class: 'GitSCM', branches: [[name: '*/release-2.10.0']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'hawk']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'myId', url: 'https://github.com/MasterAlt/sunbird-devops.git']]])

		checkout([$class: 'GitSCM', branches: [[name: '*/release-2.10.0']], extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'hawk']], userRemoteConfigs: [[url: 'https://github.com/MasterAlt/sunbird-devops.git']]])
		checkout([$class: 'GitSCM', branches: [[name: '*/release-2.10.0']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'private']], userRemoteConfigs: [[credentialsId: 'githubHarsha', url: 'https://github.com/ekstep/sunbird-devops']]])
	}

	// Have the Build 
	stage('Build'){
		echo "Run the maven commands"
	}

	// Send the sonar reports
	stage('Sonar'){
		echo "Send the sonar reports"
	}
}
