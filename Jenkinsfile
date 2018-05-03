#!/usr/bin/env groovy
//@Library('fs-my-shared-lib@master') _
@Library('my-shared-lib@feature/std_pipeline_bus_approach') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

node {
    // Clean workspace before doing anything
    deleteDir()
    varShare = "sample"
    //Chekout pipeline repo
    checkout scm

    def postBuildScript = {
        def sample = load("sample.groovy")
        sample.testPipelineExtension()
    }

    def postStageScript = {
        def sname = env.stageName
        echo "======== Completed stage END -- ${env.stageName} =========="
    }

    def preStageScript = {
        def sname = env.stageName
        echo "======== Start stage BEGIN -- ${env.stageName} =========="
    }

    customFlow {
        postBuild = postBuildScript
        //preStage = preStageScript
        postStage = postStageScript
    }
}
