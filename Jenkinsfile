node{
	stage('Checkout'){
        new File('one').mkdir()
        new File('two').mkdir()
        new File('three').mkdir()
	
    dir ('one') {
        git branch: "release-2.10.0", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-devops.git'
    }
    dir ('two') {
        git branch: "release-2.7.0_RC1", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-data-pipeline'
    }
	}
}
