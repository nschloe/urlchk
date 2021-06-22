<p align="center">
  <a href="https://github.com/nschloe/deadlink"><img alt="deadlink" src="https://nschloe.github.io/deadlink/logo.svg" width="60%"></a>
</p>

[![PyPi Version](https://img.shields.io/pypi/v/deadlink.svg?style=flat-square)](https://pypi.org/project/deadlink/)
[![PyPI pyversions](https://img.shields.io/pypi/pyversions/deadlink.svg?style=flat-square)](https://pypi.org/project/deadlink/)
[![GitHub stars](https://img.shields.io/github/stars/nschloe/deadlink.svg?style=flat-square&logo=github&label=Stars&logoColor=white)](https://github.com/nschloe/deadlink/)
[![PyPi downloads](https://img.shields.io/pypi/dm/deadlink.svg?style=flat-square)](https://pypistats.org/packages/deadlink)

[![gh-actions](https://img.shields.io/github/workflow/status/nschloe/deadlink/ci?style=flat-square)](https://github.com/nschloe/deadlink/actions?query=workflow%3Aci)
[![codecov](https://img.shields.io/codecov/c/github/nschloe/deadlink.svg?style=flat-square)](https://app.codecov.io/gh/nschloe/deadlink)
[![LGTM](https://img.shields.io/lgtm/grade/python/github/nschloe/deadlink.svg?style=flat-square)](https://lgtm.com/projects/g/nschloe/deadlink)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg?style=flat-square)](https://github.com/psf/black)

Parses text files for HTTP URLs and checks if they are still valid. Install with
```
pip install deadlink
```
and use as
```sh
deadlink-check README.md   # or multiple files/directories
```
To explicitly allow or ignore certain URLs, use
```
deadlink-check README.md -a http: -i stackoverflow.com github
```
This only considers URLs containing `http:` and _not_ containing `stackoverflow.com` or
`github`. You can also place allow and ignore lists in the config file
`~/.config/deadlink/config.toml`, e.g.,
```toml
allow = [
  "https:"
]
ignore = [
  "stackoverflow.com",
  "math.stackexchange.com",
  "discord.gg",
  "doi.org"
]
```
See
```
deadlink-check -h
```
for all options. Use
```
deadlink-fix path-or-file
```
to replace redirects in ann files. The same filters as for `deadlink-check` apply.

Example output:

![](https://nschloe.github.io/deadlink/example-output-carbon.png)


### License
deadlink is published under the [MIT
license](https://en.wikipedia.org/wiki/MIT_License).
