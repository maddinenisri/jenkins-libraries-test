#!/bin/groovy
@Library('my-shared-lib') _
//@Grab('org.yaml:snakeyaml:1.20')
import com.mdstech.pipeline.*

checkout scm

orchestratePipeline {
  metadata = "Json"
  build = true
  test = true
  deploy = true
}

