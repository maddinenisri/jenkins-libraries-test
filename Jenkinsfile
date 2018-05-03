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

    customFlow {
        postBuild = "java -version"
    }
}
