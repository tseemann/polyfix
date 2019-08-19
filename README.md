[![Build Status](https://travis-ci.org/tseemann/polyfix.svg?branch=master)](https://travis-ci.org/tseemann/polyfix)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Don't judge me](https://img.shields.io/badge/Language-Perl_5-steelblue.svg)

# polyfix

## Introduction

Genomes assembled from Nanopore data are imperfect.  Even at 99.9% consensus
accuracy there remains ~1 error per 1000 bp.  Given a typical bacterial gene
is ~1000 bp, this means 1 error per gene.  The most common error mode in
Nanopore is indels, usually around homopolymer regions.  This results in a
frame-shift in the gene, causing annotation tools like Prokka to find two
partial genes instead of one intact gene.

Ideally one would also sequence with Illumina and polish the assembly, as
Illumina data does not suffer from homopolymer issues.  However, if you are
unable to do that, `polyfix` is designed to take your draft Nanopore
assembly and compare it to one or more "trusted reference" genomes, and
polish out likely homopolymer errors to remove the frame-shifts. 

## Quick Start

```
% polyfix --version
polyfix 0.0.1

% polyfix --help

```

## Installation

### Conda
Install [Conda](https://conda.io/docs/) or [Miniconda](https://conda.io/miniconda.html):
```
conda install -c conda-forge -c bioconda -c defaults polyfix  # COMING SOON
```

### Homebrew
Install [HomeBrew](http://brew.sh/) (Mac OS X) or [LinuxBrew](http://linuxbrew.sh/) (Linux).
```
brew install brewsci/bio/polyfix  # COMING SOON
```

### Source
This will install the latest version direct from Github.
You'll need to add the polyfix `bin` directory to your `$PATH`,
and also ensure all the [dependencies](#Dependencies) are installed.
```
cd $HOME
git clone https://github.com/tseemann/polyfix.git
$HOME/polyfix/bin/polyfix --help
```

## Dependencies

* `perl` >= 5.26

## License

polyfix is free software, released under the
[GPL 3.0](https://raw.githubusercontent.com/tseemann/polyfix/master/LICENSE).

## Issues

Please submit suggestions and bug reports to the
[Issue Tracker](https://github.com/tseemann/polyfix/issues)

## Author

[Torsten Seemann](https://twitter.com/torstenseemann)
