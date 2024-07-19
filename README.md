# BUILD-AND-PUSH-TO-DOCKER-HUB-ACTION

GitHub Action to build container image and push to Docker Hub.

## Usage

``` yaml
steps:
  -
    name: 'Checkout repository'
    uses: actions/checkout@v4
  -
    name: 'Build and push image'
    uses: rtvu/build-and-push-to-docker-hub-action@v2.0.0
    with:
      image: ${{ github.repository }}
      platforms: linux/amd64
      tags: version1,version2
      token: ${{ secrets.DOCKER_HUB_TOKEN }}
      username: ${{ secrets.DOCKER_HUB_USERNAME }}
```

## Inputs

| Name        | Description                                 | Default  |
| ----------- | ------------------------------------------- | -------- |
| `image`     | Name of image with format `<OWNER>/<IMAGE>` |          |
| `latest`    | Include `latest` tag                        | `false`  |
| `platforms` | Comma separated list of target platforms    |          |
| `tags`      | Comma separated list of tags for image      |          |
| `token`     | Docker Hub token                            |          |
| `username`  | Docker Hub username                         |          |
