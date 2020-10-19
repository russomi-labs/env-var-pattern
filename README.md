# env-var-pattern

- [env-var-pattern](#env-var-pattern)
  - [About](#about)
  - [Goals](#goals)
  - [History](#history)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installing](#installing)
  - [Usage](#usage)
  - [Related](#related)
    - [Python](#python)
    - [Javascript](#javascript)
  - [References](#references)

## About

The [twelve-factor app stores config in environment
variables](https://12factor.net/config) (often shortened to env vars or env).
Env vars are easy to change between deploys without changing any code; unlike
config files, there is little chance of them being checked into the code repo
accidentally; and unlike custom config files, or other config mechanisms such as
Java System Properties, they are a language- and OS-agnostic standard.

Another aspect of config management is grouping. Sometimes apps batch config
into named groups (often called "environments") named after specific deploys,
such as the development, test, and production environments in Rails. This method
does not scale cleanly: as more deploys of the app are created, new environment
names are necessary, such as staging or qa. As the project grows further,
developers may add their own special environments like joes-staging, resulting
in a combinatorial explosion of config which makes managing deploys of the app
very brittle.

In a twelve-factor app, env vars are granular controls, each fully orthogonal to
other env vars. They are never grouped together as "environments", but instead
are independently managed for each deploy. This is a model that scales up
smoothly as the app naturally expands into more deploys over its lifetime.

See [The Twelve-Factor App](https://12factor.net/) for additional details.

## Goals

- Using .env files with Python
- Using .env files with Javascript

## History

> An environment variable is a dynamic-named value that can affect the way running
> processes will behave on a computer. They are part of the environment in which a
> process runs. For example, a running process can query the value of the `TEMP`
> environment variable to discover a suitable location to store temporary files,
> or the `HOME` or `USERPROFILE` variable to find the directory structure owned by the
> user running the process.

> They were introduced in their modern form in 1979 with Version 7 Unix, so are
> included in all Unix operating system flavors and variants from that point
> onward including Linux and macOS. From PC DOS 2.0 in 1982, all succeeding
> Microsoft operating systems, including Microsoft Windows, and OS/2 also have
> included them as a feature, although with somewhat different syntax, usage and
> standard variable names.

See [Environment variable](https://en.wikipedia.org/wiki/Environment_variable) for
more information.

## Getting Started

These instructions will get you a copy of the project up and running on your
local machine for development and testing purposes. See
[deployment](#deployment) for notes on how to deploy the project on a live
system.

### Prerequisites

What things you need to install the software and how to install them.

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env
running.

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a
little demo.

## Usage

Add notes about how to use the system.

## Related

### Python

- https://github.com/sobolevn/dump-env - A utility tool to create .env files
- https://github.com/rochacbruno/dynaconf - Configuration Management for Python
- https://github.com/theskumar/python-dotenv - Get and set values in your .env file in local and production servers
  - https://pypi.org/project/python-dotenv/
- https://github.com/sloria/environs - simplified environment variable parsing
- https://github.com/rconradharris/envparse - Environment Variable Parsing for Python
- https://github.com/wemake-services/dotenv-linter

### Javascript

- https://www.npmjs.com/package/dotenv
- https://www.npmjs.com/package/dotenv-flow
- https://www.npmjs.com/package/dotenv-defaults

## References

- https://12factor.net/
- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/customize-containers.html
- https://create-react-app.dev/docs/adding-custom-environment-variables/
- https://nextjs.org/docs/basic-features/environment-variables
