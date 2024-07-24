# Charts
[Helm](https://github.com/helm/helm) Charts for Kubernetes

Charts are curated application definitions for [Helm](https://github.com/helm/helm). Use this repository to submit kubernetes helm Charts. 

## Repository Structure

This repository contains the source for the packaged and versioned charts (released in the [Github Pages](https://github.com/jyotibhanot/helm-charts/releases)).
The Charts in the `stable/` directory in the main branch match the latest packaged Chart in the [Chart Repository](https://github.com/jyotibhanot/helm-charts/).

The purpose of this repository is to provide a place for maintaining and contributing Helm Charts, with CI processes in place for managing the releasing of Charts into the Chart Repository.

## Validation and Release Process

### Chart Validation

We use GitHub Actions to validate our charts to ensure they meet the required standards before merging. The validation process runs on every push to branches starting with `feat/`.

### Chart Release

Once the charts pass validation, they can be released. The release process runs on every push to the `main` branch.


## Contributing a Chart
Take a look at the [aws-ebs-csi-driver](https://github.com/jyotibhanot/helm-charts/tree/main/stable/aws-ebs-csi-driver) for reference when you're writing your first few charts.

Before contributing a Chart, become familiar with the format. Note that the project is still under active development and the format may still evolve a bit.
