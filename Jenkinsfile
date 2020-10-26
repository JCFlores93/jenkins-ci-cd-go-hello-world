pipeline{
    agent any
    stages{
        stage("Script step"){
            steps{
                script {
                    def browsers = ["chrome", "firefox"]
                    for (int i =0; i < browsers.size(); i++) {
                        echo "Testing ${browsers[i]} browser"
                    }
                }
            }
        }
    }
}