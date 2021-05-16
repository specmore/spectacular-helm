# Spectacular &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/specmore/spectacular/blob/master/LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/specmore/spectacular/blob/master/CONTRIBUTING.md#your-first-pull-request)
Keep your interface specifications Spectacular!

Spectacular helps to make the change review process for interface specifications more visible and organised, resulting in the healthier evolution of interfaces. Ultimately fostering an "API First" culture.

## Key Features
* Integration with GitHub for user login and access control to your interface spec files.
* Ability to organise your interface spec files into "Catalogues", making them easier to find.
* Track upcoming versions of the spec files being drafted and what changes are being proposed by visualising all changes on an evolutionary timeline.
* Visualising your interface specifications using graphical documentation tools like [Swagger UI](https://github.com/swagger-api/swagger-ui) for OpenAPI files.

## View the Spectacular Demo
Checkout Spectacular in action by visiting our Spectacular Demo website: [https://spectacular-demo.specmore.org/](https://spectacular-demo.specmore.org/)

The demo website is deployed using this helm chart. It is configured to integrated with our own demo GitHub App installed on the [specmore/spectacular-demo](https://github.com/specmore/spectacular-demo) GitHub repository.

## Configuration
The following table lists the configuration values that can be set when releasing the Spectacular chart. Please see the Spectacular app's [Configuration guide](https://github.com/specmore/spectacular/blob/master/docs/configuration.md) for more information on how to set the require environment variables.

Parameter | Description | Default
--- | --- | ---
`githubAppId` | (Required) Sets the GITHUB_APP_ID environment variable config value. Set according to your GitHub App page. | `'70007'` (our demo app)
`githubAppInstallationId` | (Required) Sets the GITHUB_APP_INSTALLATION_ID environment variable config value. Set according to your GitHub organisations installation of your GitHub App. | `'9995096'` (our demo installation)
`githubClientId` | (Required) Sets the `client_id` part of the LOGINSRV_GITHUB environment variable config value. Set according to your GitHub App page. | `Iv1.a37ef4ddfbd85d96` (our demo app)
`githubClientSecret` | (Required) Sets the `client_secret` part of the LOGINSRV_GITHUB environment variable config value. Set according to your GitHub App page. | `46474a20eda30ee93df8b2e33fb448e1f482a2bf` (our demo app)
`authJwtSharedSecret` | (Optional) Sets the LOGINSRV_JWT_SECRET and JWT_SHARED_SECRET environment variable config values. Needs to be a 32 byte value. Will be generated if not set. | `57db0a7b4cbf1182832f377239a25a52`
`githubAppPrivateKey` | (Required) Sets the file contents of the GITHUB_APP_PRIVATE_KEY_FILE_PATH environment variable config value. Set according to the generated private key downloaded from your GitHub App page. | **...** (a key for our demo app)
`managedCertificate` | (Optional) The name of a GCP managed certificate to be used with the ingress. | none
`staticIpName` | (Optional) The name of a reserved global static IP address to be used with the ingress. | none
`clusterIssuer` | (Optional) The name of a cert-manager 'clusterissuer' resource to use with the ingress to get a tls certificate issued. | none
`hostName` | (Optional) The hostname (DNS) to be used with the ingress rules. | none
`releaseCandidateTag` | (Optional) The tag of a release candidate build to be deployed. | none

## Application Version
This chart deploys the full Spectacular system.

## Changelog
### v0.2.6
- Change deployments to use new Spectacular app v0.2.3 images.

### v0.2.5
- Change deployments to use new Spectacular app v0.2.2 images.
  
### v0.2.4
- Change deployment to use Loginsrv release with `latest` tag.
- Change deployments to use new Spectacular app v0.2.1 images.

### v0.2.3
- Change deployments to use new Spectacular app v0.2.0 images.
 
### v0.2.2
- Change deployments to use new Spectacular app v0.1.2 images.

### v0.2.1
- Change deployments to use new Spectacular app v0.1.1 images.

### v0.2.0
- Add `clusterIssuer` and `hostName` configuration values to configure ingress to support [cert-manager](https://cert-manager.io/) TLS certificates.
- Add `releaseCandidateTag` configuration value for deploying release candidate images.

### v0.1.0
Initial release set to deploy Spectacular v0.1.0.
