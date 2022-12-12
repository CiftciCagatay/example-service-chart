def updatedVersionNumber = ""

pipeline {
  environment {
    REGISTRY = "us-central1-docker.pkg.dev"
    CHART = "testchart"
    CHART_SSH = "git@github.com:lilt/helm-ci-jenkins-pipeline-demo.git"
    CHART_DIRECTORY = "charts/testchart"
    PROJECT = "lilt-development"
    REPOSITORY = "charts"
  }

  stages {
    stage("Test changeset") {
        when {
            anyOf {
                changeset 'charts/templates/*'
                changeset 'charts/values.yaml'
            }
        }

        steps {
            echo "Chart change"
        }
    }
}
