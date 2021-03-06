Codecov Global Python Uploader [![codecov.io](https://codecov.io/github/codecov/codecov-python/coverage.svg?branch=master)](https://codecov.io/github/codecov/codecov-python)
=======
| [https://codecov.io/][1] | [@codecov][2] | [hello@codecov.io][3] |
| ------------------------ | ------------- | --------------------- |

Find coverage reports for all the [languages below](#languages), gather them and submit them to Codecov.

## Codecov Features
- Reports are **automatically** combined with no extra setup. Each build is store, seperately and combined.
- Multiple languages are supported in a single upload and repository.
- *Optionally* store environment variables per build


## Usage

```sh
pip install --user codecov && codecov --token=<repo token>
```
> `--user` argument not needed for Python projects. [See example here](https://github.com/codecov/example-python).

## Languages
> [Python](https://github.com/codecov/example-python), [C#/.net](https://github.com/codecov/example-csharp), [Java](https://github.com/codecov/example-java), [Node/Javascript/Coffee](https://github.com/codecov/example-node),
> [C/C++](https://github.com/codecov/example-c), [D](https://github.com/codecov/example-d), [Go](https://github.com/codecov/example-go), [Groovy](https://github.com/codecov/example-groovy), [Kotlin](https://github.com/codecov/example-kotlin),
> [PHP](https://github.com/codecov/example-php), [R](https://github.com/codecov/example-r), [Scala](https://github.com/codecov/example-scala), [Xtern](https://github.com/codecov/example-xtend), [Xcode](https://github.com/codecov/example-xcode), [Lua](https://github.com/codecov/example-lua) and more...

## Using `tox`?
Codecov can be ran from inside your `tox.ini` please make sure you pass all the necessary environment variables through:

```
[testenv]
passenv = CI TRAVIS_BUILD_ID TRAVIS TRAVIS_BRANCH TRAVIS_JOB_NUMBER TRAVIS_PULL_REQUEST TRAVIS_JOB_ID TRAVIS_REPO_SLUG TRAVIS_COMMIT
deps = codecov>=1.4.0
commands = codecov -e TOXENV
```
> See all the environment variable for other CI providers [here](https://github.com/codecov/codecov-python/blob/master/codecov/__init__.py#L260-L430)


## Configuration
> Below are most commonly used settings.

| Argument |   Environment   |                                                                    Description                                                                     |
| -------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-t`     | `CODECOV_TOKEN` | Private repo token for uploading                                                                                                                   |
| `-e`     | `CODECOV_ENV`   | List of config vars to store for the build [see example](https://codecov.io/github/pyca/cryptography?ref=d47946f3d3e358b706e996d0b951d496ffc2461f) |

```yaml
# public repository on Travis CI
install:
  - pip install --user codecov
after_success:
  - codecov
```

```yaml
# private repository on Travis CI
install:
  - pip install --user codecov
after_success:
  - codecov -t :repo-token
```


## CI Providers
|                       Company                       |                                                                                     Supported                                                                                      |  Token Required  |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| [Travis CI](https://travis-ci.org/)                 | Yes [![Build Status](https://secure.travis-ci.org/codecov/codecov-python.svg?branch=master)](http://travis-ci.org/codecov/codecov-python)                                          | Private only     |
| [CircleCI](https://circleci.com/)                   | Yes                                                                                                                                                                                | Private only     |
| [Codeship](https://codeship.com/)                   | Yes                                                                                                                                                                                | Public & Private |
| [Jenkins](https://jenkins-ci.org/)                  | Yes                                                                                                                                                                                | Public & Private |
| [Semaphore](https://semaphoreci.com/)               | Yes                                                                                                                                                                                | Public & Private |
| [Drone.io](https://drone.io/)                       | Yes                                                                                                                                                                                | Public & Private |
| [AppVeyor](http://www.appveyor.com/)                | Yes [![Build status](https://ci.appveyor.com/api/projects/status/sw18lsj7786bw806/branch/master?svg=true)](https://ci.appveyor.com/project/stevepeak/codecov-python/branch/master) | Public & Private |
| [Wercker](http://wercker.com/)                      | Yes                                                                                                                                                                                | Public & Private |
| [Magnum CI](https://magnum-ci.com/)                 | Yes                                                                                                                                                                                | Public & Private |
| [Shippable](http://www.shippable.com/)              | Yes                                                                                                                                                                                | Public & Private |
| [Gitlab CI](https://about.gitlab.com/gitlab-ci/)    | Yes                                                                                                                                                                                | Public & Private |
| [Snap CI](https://snap-ci.com/)                     | Yes                                                                                                                                                                                | Public & Private |
| git / mercurial                                     | Yes (as a fallback)                                                                                                                                                                | Public & Private |
| [Buildbot](http://buildbot.net/)                    | `coming soon` [buildbot/buildbot#1671](https://github.com/buildbot/buildbot/pull/1671)                                                                                             |                  |
| [Bamboo](https://www.atlassian.com/software/bamboo) | `coming soon`                                                                                                                                                                      |                  |
| [Solano Labs](https://www.solanolabs.com/)          | `coming soon`                                                                                                                                                                      |                  |

> Using **Travis CI**? Uploader is compatable with `sudo: false` which can speed up your builds. :+1:



[1]: https://codecov.io/
[2]: https://twitter.com/codecov
[3]: mailto:hello@codecov.io

## Copyright

> Copyright 2014-2015 codecov
