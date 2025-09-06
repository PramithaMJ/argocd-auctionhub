# argocd-auctionhub

This repository is used as the deployment configuration source for the AuctionHub microservices on Kubernetes, managed by Argo CD.

## Purpose

- Acts as the listener repository for Argo CD.
- Updated automatically by the [auction-microservice](https://github.com/PramithaMJ/auction-microservice) repository workflow.
- Triggers the continuous deployment (CD) pipeline when changes are pushed.

## Structure

- `jenkins/`: Contains Jenkins pipeline configuration.
- `k8s/`: Contains all Kubernetes manifests, including deployments, services, configmaps, secrets, ingress, monitoring, and infrastructure resources.

## Usage

- Do not manually edit files unless necessary; updates are managed by the workflow in the auction-microservice repository.
- Argo CD monitors this repository and applies changes to the Kubernetes cluster automatically.

## How it works

1. The auction-microservice workflow updates Kubernetes manifests in this repository.
2. Argo CD detects changes and synchronizes the cluster state accordingly.
3. Jenkins pipeline can be used for additional CI/CD steps if required.

## Notes

- Ensure Argo CD is configured to watch this repository for deployment automation.
- For secrets, use the provided example file in `k8s/secrets/` and follow your organization's secret management practices.
