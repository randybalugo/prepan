# How to setup local development environment

You need to do three steps to develop PrePAN; setup local database, setup config file and install dependency.

## Clone this repository

```sh
$ git clone git://github.com/CPAN-API/prepan.git
$ cd prepan
```

## carton

PrePAN is utilizing [carton](https://metacpan.org/module/MIYAGAWA/carton-v0.9.10/docs/carton.pod) to manage module dependencies. Install dependencies via carton:

```sh
$ cpanm carton
```

## Local database setting

There is a setup script for database setting. Please run below code at PrePAN root directory.
It also setup database for test.

```sh
$ ./script/setup.sh
```

## Local config file setting

There is the example config file, which is local/development.eg.pl.  Copy and replace it.

```sh
$ cp local/development.eg.pl local/development.pl
```
And replace local/development.pl for your environment, for example twitter consumer key and so on.

# How to start local server
You can use plackup command to start local server.  Please run below at PrePAN root directory.

```sh
$ carton exec -- plackup
```

Enjoy Hacking!!

## Local test setting

Run below command if you want to run tests.

```sh
$ carton exec -- prove -v t/**/*.t
```

## Update dependency

Edit cpanfile and run following commands if you want to update dependency.

```sh
$ carton install
$ git add cpanfile cpanfile.snapshot
$ git commit
```

## Contact

You can ask [@prepanorg](http://twitter.com/prepanorg/) or [@shiba_yu36](http://twitter.com/shiba_yu36/) if you have a question.
