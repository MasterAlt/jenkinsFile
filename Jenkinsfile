node{
    def exists = fileExists 'one'
    if (!exists){
        new File('one').mkdir()
    }
    dir ('one') {
        git branch: "release-2.10.0", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-devops.git'
    }
    def exists = fileExists 'two'
    if (!exists){
        new File('two').mkdir()
    }
    dir ('one') {
        git branch: "release-2.7.0_RC1", changelog: false, poll: false, url: 'https://github.com/MasterAlt/sunbird-data-pipeline'
    }
}
