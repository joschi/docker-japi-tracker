# Java API Tracker Docker image

[![Docker Stars](https://img.shields.io/docker/stars/joschi/japi-tracker.svg)][hub]
[![Docker Pulls](https://img.shields.io/docker/pulls/joschi/japi-tracker.svg)][hub]
[![Image Size](https://images.microbadger.com/badges/image/joschi/japi-tracker.svg)][microbadger]
[![Image Version](https://images.microbadger.com/badges/version/joschi/japi-tracker.svg)][microbadger]
[![Image License](https://images.microbadger.com/badges/license/joschi/japi-tracker.svg)][microbadger]

[hub]: https://hub.docker.com/r/joschi/japi-tracker/
[microbadger]: https://microbadger.com/images/joschi/japi-tracker

## What is Java API Tracker?

A tool to visualize the API changes timeline of a Java library

Homepage: https://github.com/lvc/japi-tracker


### Examples

Use the following command to compare the versions of a Java library (SLF4J) using the `slf4j.json` profile:
```
# docker run -v "${PWD}":/workspace --rm joschi/japi-tracker:1.3-1 japi-monitor -get -build-new slf4j.json
# docker run -v "${PWD}":/workspace --rm joschi/japi-tracker:1.3-1 japi-tracker -build slf4j.json
```

The compatibility reports will be written into the `/workspace` directory.

See https://github.com/lvc/upstream-tracker-4j for numerous example profiles.


## Profile Format

```json
{
  "Name":        "SHORT LIBRARY NAME",
  "SourceUrl":   "URL TO DOWNLOAD PACKAGES",
  "Maintainer":  "MAINTAINER NAME",
  
  "Versions": [
  {
    "Number":      "VERSION NUMBER",
    "Installed":   "INSTALL TREE PATH",
    "Source":      "SOURCE PACKAGE PATH",
    "Changelog":   "CHANGELOG: On/Off",
    "PkgDiff":     "PACKAGE DIFF: On/Off"
  },
  
  ...
  
  {
      ...
  }]
}
```

## License

This Docker image is licensed under the MIT license, see [LICENSE](LICENSE).
