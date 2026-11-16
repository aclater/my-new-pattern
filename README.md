# Multicloud Gitops

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Azure](https://img.shields.io/endpoint?url=https%3A%2F%2Fstorage.googleapis.com%2Fhcp-results%2Fmcgitops-azr-ci.json)](https://storage.googleapis.com/hcp-results/mcgitops-azr-ci.json)
[![GCP](https://img.shields.io/endpoint?url=https%3A%2F%2Fstorage.googleapis.com%2Fhcp-results%2Fmcgitops-gcp-ci.json)](https://storage.googleapis.com/hcp-results/mcgitops-gcp-ci.json)

## Start Here

If you've followed a link to this repository, but are not really sure what it contains
or how to use it, head over to [Multicloud GitOps](http://hybrid-cloud-patterns.io/multicloud-gitops/)
for additional context and installation instructions

## Quick start

You need an OpenShift 4 cluster, a kubeconfig logged in to it as a cluster administrator, git and Podman.
`pattern.sh` runs `make` inside the patterns utility container, so nothing else is needed on your machine.

1. Get the pattern and create the secrets file it loads into the vault:

   ```
   git clone https://github.com/aclater/my-new-pattern.git
   cd my-new-pattern
   cp values-secret.yaml.template ~/values-secret.yaml
   ```

2. Render what will be installed, without touching a cluster:

   ```
   ./pattern.sh make show
   ```

3. Install the pattern on the cluster your kubeconfig points at:

   ```
   ./pattern.sh make install
   ```

Step 3 has not yet been tested. `./pattern.sh make help` lists the other tasks. To change what the pattern deploys,
fork this repository and clone your fork instead: the cluster follows the repository and branch you install from.
