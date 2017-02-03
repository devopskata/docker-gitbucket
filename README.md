docker-gitbucket
================

## DevOps Katas

This Gitbucket image has been modified to store its state internally.  It is pre-configured to work with the DevOps Katas Learning VM.

Setup a container with [GitBucket](https://github.com/takezoe/gitbucket) installed.

## Usage

To run the container, do the following:

```
% docker run -d -p 8080:8080 -p 29418:29418 devopskatas/gitbucket_image
```

You can see gitbucket running on http://localhost:8080/
You also see gitbucket data write out to "./gitbucket-data".

In order to access the git repository over SSH (port 29418), check settings below.

- GitBucket > Administration > System Settings > SSH access

Additional environment variables can be set as below.

Environment variable | Value | Example
---------------------|-------|--------
`GITBUCKET_DB_URL`, `GITBUCKET_DB_USER`, `GITBUCKET_DB_PASSWORD` | Database connection for MySQL or PostgreSQL. See [External database configuration](https://github.com/gitbucket/gitbucket/wiki/External-database-configuration). Defaults to H2. | `jdbc:postgresql://db/gitbucket`, `user`, `password`
`JAVA_OPTS`         | JavaVM options.     | `-Xmx1g`
`GITBUCKET_OPTS`    | GitBucket options.  | `--prefix=/gitbucket`

## Building

To build the image, do the following:

```
% docker build github.com/f99aq8ove/docker-gitbucket
```

A prebuilt container is available in the docker index.

```
% docker pull f99aq8ove/gitbucket
```

## GitBucket's license
see https://github.com/takezoe/gitbucket
