#!/usr/bin/env groovy
@Library('my-shared-lib@feature/std_pipeline_bus_approach') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

node {
    // Clean workspace before doing anything
    deleteDir()

    //Chekout pipeline repo
    checkout scm

    pipelineFlow {
        definition = "pipeline.yaml"
        metadata = "metadata/test_metadata.json"
    }


//    orchestratePipeline {
//      metadata = "metadata/test_metadata.json"
//      build = "build_config.json"
//      artifactory = "artifactory_config.yaml"
//      test = true
//      deploy = true
//    }
}
