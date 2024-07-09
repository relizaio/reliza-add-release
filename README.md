# `reliza-add-release`

## About
This action, uses the RelizaHub CLI, [`reliza-cli`](https://github.com/relizaio/reliza-cli), to submit the release metadata.
This action should always be used after the [`reliza-get-version`](https://github.com/relizaio/reliza-get-version) action.

## Usage

Submit Release metadata:

```yaml
steps:
- uses: relizaio/reliza-add-release@1.2
  with:
    reliza_api_id: <api-id-obtained-from-relizahub>
    reliza_api_key: <api-key-obtained-from-relizahub>
    image_full_name: <registry/owner/image>
    image_digest: <api-key-obtained-from-relizahub>
    reliza_full_version: <version obtained on get-version step>
    reliza_build_start: <build start time recorded on get-version step>
    reliza_build_status: <complete|rejected>
```

## Inputs
The actions supports the following inputs:

- `reliza_api_id`: The project API ID obtained from RelizaHub.
- `reliza_api_key`: The project API Key obtained from RelizaHub.
- `image_full_name`: Full name of the Docker image with registry prefix
- `image_name`: Name of the image
- `image_digest`: SHA 256 digest of the image artifact
- `reliza_full_version`: Version obtained from RelizaHub for this release
- `reliza_build_start`: Build start time
- `reliza_build_status`: Build status - `complete` - if build succeded,  `rejected` - if build failed
- `artifact_type`: Type of artifact created by this release [Docker, File] (Optional)
- `commit_list`: List of commits (Optional)
- `enable_sbom`: Enables SBOM generation using cdxgen (Optional)
- `registry_username`: Username for the image registry. (Optional - needed for sbom generation)
- `registry_password`: Password for the image registry. (Optional - needed for sbom generation)
- `registry_host`: Image registry host. (Optional - needed for sbom generation)
- `path`: Path to the relative to root of the repo (default is '.').
 (Optional - needed for sbom generation)
