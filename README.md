# dkron-cli

[![Build Status](https://travis-ci.org/Eyjafjallajokull/dkron-cli.svg?branch=master)](https://travis-ci.org/Eyjafjallajokull/dkron-cli)

Command line interface client for [Dkron](http://dkron.io/).

## Prerequisites

* Pytnon 3

## Installing

To install use pip:

```console
pip install dkron-cli
```

Or clone the repo:

```console
git clone https://github.com/Eyjafjallajokull/dkron-cli.git
python setup.py install
```

## Usage

Before you begin, set environment variable `DKRON_API_URL` to point running dkron instance.

```console
export DKRON_API_URL=http://my-dkron.example.com
```

Alternatively, you can instert `--url` argument to every invocation of dkron-cli.

#### Fetch all jobs

```console
dkron-cli get jobs
```

It works well with `jq`, to list all job names:

```console
dkron-cli get jobs | jq '.[].name'
```

#### Fetch specific job

```console
dkron-cli get job [job_name]
```

#### Create or update job

```console
dkron-cli apply job [json_file] ...
```

You can pass multiple files at once.

#### Execute job

```console
dkron-cli run [job_name]
```

#### Delete job

```console
dkron-cli delete job [job_name]
```

#### Cluster status

```console
dkron-cli get status
dkron-cli get leader
dkron-cli get members
```

## Running tests

```console
make test
make coverage
```
