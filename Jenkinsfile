#!/usr/bin/env groovy
//@Library('fs-my-shared-lib@master') _
@Library('my-shared-lib@feature/std_pipeline_bus_approach') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

node {
    // Clean workspace before doing anything
    deleteDir()

    //Chekout pipeline repo
    checkout scm

    def postBuildScript = {
        def sample = load("sample.groovy")
        sample.testPipelineExtension()
    }

    def postStageScript = {
        echo "======== Competed stage END =========="
    }

    customFlow {
        postBuild = postBuildScript
        postStage = postStageScript
    }
}
