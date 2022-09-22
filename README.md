<img src="./opencost-header.png"/>

# OnScale OpenCost Fork

This branch provides the changes to the `onscale` branch which are [OnScale](http://www.onscale.com) specific.

# Statement of Work

The maintainer of this repo, [ryanpeach](https://github.com/ryanpeach) firmly believes that cost monitoring should be free. Cost monitoring should not cost money, because to pay to save money or to calculate spend is a conflict of interests.

No GUI code will be supported, instead focusing on grafana and other prometheus stack tools to provide the UI and monitoring framework.

# Contribution

**We need to ensure the `develop` branch can sync upstream and downstream with [opencost/opencost](https://github.com/opencost/opencost)**


Rules:

* The `develop` branch should stay syncronized with `opencost/opencost:develop`.

* `feature` branches should branch from `develop`. If you don't do this you wont be able to submit the feature upstream. Never let the `develop` branch get poluted with unaccepted features or OnScale specific deployment code.

* `feature` branches should PR to `opencost/opencost:develop` AND to `onscale/opencost:onscale`

* If the PR to `opencost/opencost:develop` is accepted, you should sync `develop` with `opencost/opencost:develop` and then merge `onscale/opencost:develop` into `onscale/opencost:onscale`

**In this diagram `opencost/opencost:develop` is called `main` due to limitations of mermaid.**

```mermaid
gitGraph
  commit id: "Forked commit"
  branch develop
  checkout main
  commit id: "New opencost version"
  checkout develop
  merge main
  commit id: "Begin Development"
  branch feature
  commit id: "New feature"
  checkout develop
  merge feature
  checkout main
  merge feature
  commit id: "PR Accepted"
  checkout develop
  merge main
```

# OpenCost — your favorite open source cost monitoring tool for Kubernetes

OpenCost models give teams visibility into current and historical Kubernetes spend and resource allocation. These models provide cost transparency in Kubernetes environments that support multiple applications, teams, departments, etc.


OpenCost was originally developed and open sourced by [Kubecost](https://kubecost.com). This project combines a [specification](/spec/) as well as a Golang implementation of these detailed requirements.

![OpenCost allocation UI](/allocation-drilldown.gif)

To see the full functionality of OpenCost you can view [OpenCost features](https://opencost.io). Here is a summary of features enabled:

- Real-time cost allocation by Kubernetes service, deployment, namespace, label, statefulset, daemonset, pod, and container
- Dynamic asset pricing enabled by integrations with AWS, Azure, and GCP billing APIs
- Supports on-prem k8s clusters with custom pricing sheets
- Allocation for in-cluster resources like CPU, GPU, memory, and persistent volumes.
- Allocation for AWS & GCP out-of-cluster resources like RDS instances and S3 buckets with key (optional)
- Easily export pricing data to Prometheus with /metrics endpoint ([learn more](PROMETHEUS.md))
- Free and open source distribution (Apache2 license)

## Getting Started

You can deploy OpenCost on any Kubernetes 1.8+ cluster in a matter of minutes, if not seconds!

Visit the full documentation for [recommended install options](https://www.opencost.io/docs/install). Compared to building from source, installing from Helm is faster and includes all necessary dependencies.

## Usage

- [Cost APIs](https://www.opencost.io/docs/api)
- [CLI / kubectl cost](https://www.opencost.io/docs/kubectl-cost)
- [Prometheus Metrics](https://www.opencost.io/docs/prometheus)
- Reference [User Interface](https://github.com/opencost/opencost/tree/develop/ui)

## Contributing

We :heart: pull requests! See [`CONTRIBUTING.md`](CONTRIBUTING.md) for information on building the project from source
and contributing changes.

## Community

If you need any support or have any questions on contributing to the project, you can reach us on [CNCF Slack](https://slack.cncf.io/) in the [#opencost](https://cloud-native.slack.com/archives/C03D56FPD4G) channel or via email at [team@kubecost.com](team@kubecost.com).

## FAQ

You can view [OpenCost documentation](https://www.opencost.io/docs/FAQ) for a list of commonly asked questions.
