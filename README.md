# AndroidLibXrayLite

Fork maintained for use in the [Gromozeka](https://github.com/skvarovski/gromozeka) Android VPN client.

Tracks upstream [`2dust/AndroidLibXrayLite`](https://github.com/2dust/AndroidLibXrayLite); local commits are limited to CI tweaks needed to publish `libv2ray.aar` artifacts under this fork.

## Build requirements
* JDK
* Android SDK
* Go
* gomobile

## Build instructions
1. `git clone [repo] && cd AndroidLibXrayLite`
2. `gomobile init`
3. `go mod tidy -v`
4. `gomobile bind -v -androidapi 21 -ldflags='-s -w' ./`

## CI artifact

Each push to `main` builds `libv2ray.aar` via `.github/workflows/main.yml` and uploads it as a workflow artifact (`libv2ray`). Manual `workflow_dispatch` accepts an optional `release_tag` to push the artifact to a release.
