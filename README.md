# heroku-buildpack-vips

Heroku buildpack with [libvips](https://github.com/libvips/libvips) installed. A buildpack for the modern Heroku stacks.

[![Vips](https://img.shields.io/github/v/tag/timezest/heroku-buildpack-vips?label=vips&logo=hack-the-box)](https://github.com/timezest/heroku-buildpack-vips/releases)
[![Heroku 22](https://img.shields.io/badge/stack-22-904edf?logo=heroku)](https://github.com/timezest/heroku-buildpack-vips/releases)
[![Build](https://github.com/timezest/heroku-buildpack-vips/actions/workflows/build.yml/badge.svg)](https://github.com/timezest/heroku-buildpack-vips/actions/workflows/build.yml)

## Usage

Run the commands below to add this buildpack to your app:

```
$ heroku buildpacks:add --index 1 https://github.com/timezest/heroku-buildpack-vips
```

Deploy to Heroku and verify the result by running this command:

```
$ heroku run vips -v
vips 8.14.4
```

## Configuration

You can select the preferred version by setting the `VIPS_VERSION` environment variable. Check the available versions in the [releases](https://github.com/timezest/heroku-buildpack-vips/releases) page — the buildpack can only install a version we have built and released here.

```
$ heroku config:set VIPS_VERSION=8.13.0
```

### Untrusted operations

You can block untrusted operations at runtime by setting the `VIPS_BLOCK_UNTRUSTED` environment variable. Then any operation that is tagged as untrusted will be prevented from running. More information available [here](https://www.libvips.org/2022/05/28/What's-new-in-8.13.html#blocking-of-unfuzzed-loaders).

```
$ heroku config:set VIPS_BLOCK_UNTRUSTED=true
```

## License

The buildpack is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
