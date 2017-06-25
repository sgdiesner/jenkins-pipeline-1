# Sample pipeline library

Pipeline script:
````
@Library('sgdiesner-lib') _

import nl.flusso.Utilities

def utils = new Utilities(steps)

node{

}

stage("Init"){
    node {
        echo "Job Name $JOB_NAME"
    }
}
stage("Build"){
    node {
        String name = 'Steve from /var/sayHello call()'
        sayHello name
    }
}

stage("Tests"){
    node {
        String name = 'Steve from /src/nl/flusso/Utilities class'
        utils.sayHello(name)
    }
}
```