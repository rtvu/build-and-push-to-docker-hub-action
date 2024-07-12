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
    uses: rtvu/build-and-push-to-docker-hub-action@v1.0.1
    with:
      image: ${{ github.repository }}
      platforms: linux/amd64
      tag: latest
      token: ${{ secrets.DOCKER_HUB_TOKEN }}
      username: ${{ secrets.DOCKER_HUB_USERNAME }}
```

## Inputs

| Name        | Description                               | Default |
| ----------- | ----------------------------------------- | ------- |
| `image`     | Name of image with format <OWNER>/<IMAGE> |         |
| `latest`    | Use latest tag                            | `true`  |
| `platforms` | List of target platforms to build         |         |
| `tag`       | Name of tag for image                     |         |
| `token`     | Docker Hub token                          |         |
| `username`  | Docker Hub username                       |         |
