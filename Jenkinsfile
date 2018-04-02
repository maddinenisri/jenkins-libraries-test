#!/usr/bin/env groovy
@Library('my-shared-lib') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

node {
    // Clean workspace before doing anything
    deleteDir()

    //Chekout pipeline repo
    checkout scm

    FlowOrchestrator.processStages


//    orchestratePipeline {
//      metadata = "metadata/test_metadata.json"
//      build = "build_config.json"
//      artifactory = "artifactory_config.yaml"
//      test = true
//      deploy = true
//    }
}
