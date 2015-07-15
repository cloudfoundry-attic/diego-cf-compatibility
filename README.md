# diego-cf-compatibility
This repo tracks which versions of cf-release and diego-release are known to work together.
Each row represents a group of releases that have passed some level of integration testing.

## CSV Columns

In compatibility-v1.csv, we track the following information:

### RELEASE_STAGE

Release stage documents the stage in our pipeline a given row of versions have successfully passed.

`release_candidate` indicates the releases have been successful on an integration environment shared between all Cloud Foundry products. 

`development` indicates that the releases have passed an isolated, diego-internal test environment, and are not suitable for production environments.


### DIRECTOR_VERSION

The current version of the bosh director associated with each record.
Check out the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version.

### CF_RELEASE_COMMIT_SHA

The sha of the [cf-release](https://github.com/cloudfoundry/cf-release) commit that was deployed.
More information on deploying cf-release can be found [here](http://docs.cloudfoundry.org/deploying/)

### CF_DEPLOYMENT_STEMCELL

The version of the stemcell that cf-release was deployed with.
Stemcells can be found [here](http://bosh.io/stemcells).

### DIEGO_RELEASE_VERSION // DIEGO_RELEASE_COMMIT_SHA

The version and commit sha of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed.

To check out the corresponding commit on diego release:
```
git clone https://github.com/cloudfoundry-incubator/diego-release
cd diego-release/
git checkout <DIEGO_RELEASE_VERSION>
```

### DIEGO_DEPLOYMENT_STEMCELL

The version of the stemcell that diego-release was deployed with.
Stemcells can be found [here](http://bosh.io/stemcells).
