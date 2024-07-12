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
    uses: rtvu/build-and-push-to-docker-hub-action@v1.0.0
    with:
      image: ${{ github.repository }}
      platforms: linux/amd64
      tag: latest
      token: ${{ secrets.DOCKER_HUB_TOKEN }}
      username: ${{ secrets.DOCKER_HUB_USERNAME }}
```

## Inputs

| Name        | Description                               | Required | Default |
| ----------- | ----------------------------------------- | -------- | ------- |
| `image`     | Name of image with format <OWNER>/<IMAGE> | `true`   |         |
| `latest`    | Use latest tag                            | `false`  | `true`  |
| `platforms` | List of target platforms to build         | `true`   |         |
| `tag`       | Name of tag for image                     | `true`   |         |
| `token`     | Docker Hub token                          | `true`   |         |
| `username`  | Docker Hub username                       | `true`   |         |
