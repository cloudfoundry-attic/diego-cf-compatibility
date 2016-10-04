# diego-cf-compatibility
This repo tracks which versions of cf-release and diego-release are known to work together.
Each row represents a group of releases that have passed some level of integration testing.

## CSV Columns

### v5 schema
This version of the schema provides more IaaS-specific information. No previous version continues to be updated. In `compatibility-v5.csv`, we track the following information:

| name | description |
|---|---|
| `cf-release-commit-sha` | The sha of the [cf-release](https://github.com/cloudfoundry/cf-release) commit that was deployed. More information on deploying cf-release can be found [here](http://docs.cloudfoundry.org/deploying/). |
| `diego-release-version` | The version of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed. |
| `garden-linux-release-version` | The version of [garden-linux-release](https://github.com/cloudfoundry-incubator/garden-linux-release) that was deployed on vSphere. |
| `garden-runc-release-version` | The version of [garden-runc-release](https://github.com/cloudfoundry-incubator/garden-runc-release) that was deployed on AWS and bosh-lite. |
| `etcd-release-version` | The version of [etcd-release](https://github.com/cloudfoundry-incubator/etcd-release) that was deployed. |
| `cflinuxfs2-rootfs-release-version` | The version of [cflinuxfs2-rootfs-release](https://github.com/cloudfoundry/cflinuxfs2-rootfs-release) that was deployed. |
| `bosh-lite-commit-sha` | The commit SHA of the [bosh-lite repository](https://github.com/cloudfoundry/bosh-lite) used to deploy the releases. |
| `aws-stemcell` | The version of the stemcell that the releases (cf, diego, etcd, garden-linux) were deployed with. AWS stemcells can be found [here](http://bosh.io/stemcells/bosh-aws-xen-hvm-ubuntu-trusty-go_agent). |
| `bosh-lite-stemcell` | The version of the stemcell used to deploy the releases (cf, diego, etcd, garden-linux). Bosh Lite stemcells can be found [here](http://bosh.io/stemcells/bosh-warden-boshlite-ubuntu-trusty-go_agent). |
| `vsphere-stemcell` | The version of the stemcell used to deploy the releases (cf, diego, etcd, garden-linux). vSphere stemcells can be found [here](http://bosh.io/stemcells/bosh-vsphere-esxi-ubuntu-trusty-go_agent). |
| `aws-director-version` | The version of the bosh director used to deploy the releases on AWS. See the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version. |
| `bosh-lite-director-version` | The version of the bosh director used to deploy the releases on bosh-lite. See the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version. |
| `vsphere-director-version` | The version of the bosh director used to deploy the releases on vSphere. See the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version. |
| `aws-acceptance-tests-build-url` | The URL for the latest passing acceptance tests run for this combination of artifacts on AWS in CI. |
| `bosh-lite-acceptance-tests-build-url` | The URL for the latest passing acceptance tests run for this combination of artifacts on bosh-lite in CI. |
| `vsphere-acceptance-tests-build-url` | The URL for the latest passing acceptance tests run for this combination of artifacts on vSphere in CI. |

### v4 schema (OBSOLETE)
This file is no longer updated. In `compatibility-v4.csv`, we tracked the following information:

| name | description |
|---|---|
| `cf-release-commit-sha` | The sha of the [cf-release](https://github.com/cloudfoundry/cf-release) commit that was deployed. More information on deploying cf-release can be found [here](http://docs.cloudfoundry.org/deploying/). |
| `diego-release-commit-sha` | The commit sha of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed. |
| `diego-release-version` | The version of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed. |
| `garden-linux-release-version` | The version of [garden-linux-release](https://github.com/cloudfoundry-incubator/garden-linux-release) that was deployed. |
| `etcd-release-version` | The version of [etcd-release](https://github.com/cloudfoundry-incubator/etcd-release) that was deployed. |
| `cflinuxfs2-rootfs-release-version` | The version of [cflinuxfs2-rootfs-release](https://github.com/cloudfoundry/cflinuxfs2-rootfs-release) that was deployed. |
| `director-version` | The current version of the bosh director associated with each record. Check out the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version. |
| `stemcell` | The version of the stemcell that the releases (cf, diego, etcd, garden-linux) were deployed with. Stemcells can be found [here](http://bosh.io/stemcells). |

### v3 schema (OBSOLETE)
This file is no longer updated. In `compatibility-v3.csv`, we tracked the following information:

| name | description |
|---|---|
| `director-version` | The current version of the bosh director associated with each record. Check out the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version. |
| `cf-release-commit-sha` | The sha of the [cf-release](https://github.com/cloudfoundry/cf-release) commit that was deployed. More information on deploying cf-release can be found [here](http://docs.cloudfoundry.org/deploying/). |
| `diego-release-commit-sha` | The commit sha of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed. |
| `diego-release-version` | The version of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed. |
| `garden-linux-release-version` | The version of [garden-linux-release](https://github.com/cloudfoundry-incubator/garden-linux-release) that was deployed. |
| `etcd-release-version` | The version of [etcd-release](https://github.com/cloudfoundry-incubator/etcd-release) that was deployed. |
| `stemcell` | The version of the stemcell that the releases (cf, diego, etcd, garden-linux) were deployed with. Stemcells can be found [here](http://bosh.io/stemcells). |


### v2 schema (OBSOLETE)
The v2 file is no longer updated, but can still be consumed. In compatibility-v2.csv, we track the following information:

#### DATE

Time at which the compatibility record was recorded.


#### RELEASE_STAGE

Release stage documents the stage in our pipeline a given row of versions have successfully passed.

`release_candidate` indicates the releases have been successful on an integration environment shared between all Cloud Foundry products.

`development` indicates that the releases have passed a test environment specific to the Diego team, and are not necessarily suitable for production environments.


#### DIRECTOR_VERSION

The current version of the bosh director associated with each record.
Check out the [BOSH documentation](https://bosh.io/docs) for more information on how to deploy a specific director version.


#### CF_RELEASE_COMMIT_SHA

The sha of the [cf-release](https://github.com/cloudfoundry/cf-release) commit that was deployed.
More information on deploying cf-release can be found [here](http://docs.cloudfoundry.org/deploying/).


#### CF_DEPLOYMENT_STEMCELL

The version of the stemcell that cf-release was deployed with.
Stemcells can be found at [bosh.io](http://bosh.io/stemcells).


#### DIEGO_RELEASE_VERSION // DIEGO_RELEASE_COMMIT_SHA

The version and commit sha of [diego-release](https://github.com/cloudfoundry-incubator/diego-release) that was deployed.

To check out the corresponding commit on diego-release:
```
git clone https://github.com/cloudfoundry-incubator/diego-release
cd diego-release/
git checkout <DIEGO_RELEASE_VERSION>
```

#### DIEGO_DEPLOYMENT_STEMCELL

The version of the stemcell on which diego-release was deployed.
Stemcells can be found at [bosh.io](http://bosh.io/stemcells).

#### GARDEN_LINUX_RELEASE_VERSION

The version of [garden-linux-release](https://github.com/cloudfoundry-incubator/garden-linux-release) that was deployed.

To check out the corresponding commit on garden-linux release:
```
git clone https://github.com/cloudfoundry-incubator/garden-linux-release
cd garden-linux-release/
git checkout <GARDEN_LINUX_RELEASE_VERSION>
```

#### ETCD_RELEASE_VERSION

The version of [etcd-release](https://github.com/cloudfoundry-incubator/etcd-release) that was deployed.

To check out the corresponding commit on etcd-release:
```
git clone https://github.com/cloudfoundry-incubator/etcd-release
cd etcd-release/
git checkout <ETCD_RELEASE_VERSION>
```
