---
layout: single
title:  "wkdict: A CLI dictionary app in your terminal app"
date:   2019-02-03 17:44:45 -0700
categories: Programming
tags: [open-source]
toc: true
publish: true
---

[![PyPI version](https://badge.fury.io/py/wkdict.svg)](https://badge.fury.io/py/wkdict)
[![Build Status](https://travis-ci.org/jiaowoshabi/wkdict.svg?branch=master)](https://travis-ci.org/jiaowoshabi/wkdict)
[![GitHub stars](https://img.shields.io/github/stars/jiaowoshabi/wkdict.svg)](https://github.com/wenhaoz-fengcai/wkdict/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/jiaowoshabi/wkdict.svg)](https://github.com/wenhaoz-fengcai/wkdict/network)
[![GitHub issues](https://img.shields.io/github/issues/jiaowoshabi/wkdict.svg)](https://github.com/wenhaoz-fengcai/wkdict/issues)
[![GitHub license](https://img.shields.io/github/license/jiaowoshabi/wkdict.svg)](https://github.com/wenhaoz-fengcai/wkdict/blob/master/LICENSE)

Happy Chinese Spring Festival 2019! A new year gift for my beloved open-source community: a light-weight text-based dictionary application called, [wkdict](https://pypi.org/project/wkdict/) has just been released for this special occasion! This cross-platform program talks with Wiktionary's [API](https://www.wiktionary.org) with the requested query(i.e. A single English word), and parses the returned JSON object in to a clean and readable format. The following snapshot gives you a taste of what this application looks like:

![](https://s3-us-west-1.amazonaws.com/blogassetswenhao/wkdict/Screen+Shot+2019-05-22+at+10.20.04+PM.png)

## Install on Mac/Linux

Make sure you have the python3 installed on your machine, and use the following command to install `wkdict`

```
pip3 install wkdict
```

## Usage

In terminal, run the application using 

```
wkdict "word-you-wanna-lookup"
```

For example, `wkdict love` will give you the following result:

```
1) love	(UK, US) IPA: /lʌv/
   🏷  noun

	📗 Definitions
	☞ love (countable and uncountable, plural loves)
	☞ (uncountable) Strong affection.
	☞ (countable) A person who is the object of romantic feelings; a
	  darling, a sweetheart, a beloved.

	📘 Examples
	➡ A mother’s love is not easily shaken.
	➡ My husband’s love is the most important thing in my
	  life.
	➡ He on his side / Leaning half-raised, with looks of
	  cordial love / Hung over her enamoured.
...
``` 

## Command options

```
Usage: wkdict [OPTIONS] WORD

Options:
  --limit INTEGER  Maximum number of entries/examples shown.  [default: 3]
  --version        Show the version and exit.
  --help           Show this message and exit.
```

## Changelog

Curren app version(master branch) is `0.1.0`.

Changes in current version:

* Better formatting of dictionary entries
* Add unicode support
* Add test cases
* Add Command-Line Options



