#!/usr/bin/env groovy
@Library('my-shared-lib') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

node {
    // Clean workspace before doing anything
    deleteDir()

    //Chekout pipeline repo
    checkout scm

    def localEnvParams = []
    localEnvParams.add("JAVA_HOME=${ tool 'jdk-1.8' }")
    localEnvParams.add("PATH+MAVEN=${tool 'maven-3.3.9'}/bin:${env.JAVA_HOME}/bin")

    def buildCondition=[:]
    buildCondition.element="build.existingArtifactVersion"
    buildCondition.condition="NOT_PRESENT"

    def buildCommands = []
    buildCommands.add("clean install")

    def buildParams = [:]
    buildParams.currentDirectory="src"
    buildParams.localEnvParams = localEnvParams
    buildParams.buildCondition=buildCondition
    buildParams.buildCommands=buildCommands

    orchestratePipeline {
      metadata = "metadata/test_metadata.json"
      build = buildParams
      test = true
      deploy = true
    }
}
