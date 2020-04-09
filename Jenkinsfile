node{
	stage('Checkout'){
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
    	    git branch: "release-2.7.0", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-data-pipeline,git'
    	}
    	dir ('three') {
    	    git branch: "master", changelog: false, poll: false, url: 'https://github.com/smyaltamash/king.git'
    	}
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
