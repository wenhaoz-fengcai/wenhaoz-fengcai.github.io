---
layout: single
title:  "My first contribution experience on open-source community"
date:   2018-06-13 14:22:45 -0700
categories: Programming
tags: [open-source]
toc: true
publish: true
---
# Try my first contribution on **scikit-learn**

Well, having this idea of giving back to open-source community for almost half a year, today I finally have some spare time and courage to take my first trial on fixing bugs for a popular open-source machine learning project, [scikit-learn](http://scikit-learn.org). The first issue I tried is trivial and nothing fancy. The issue is a compatibility with Python 3.7.0b5 causing by [this bug](https://bugs.python.org/issue30399). But I decided to blog down every details while I'm doing it, just to show how I'm doing it, hopefully, paving the way for whoever wants to make contribution to open-source projects in the future.  

## Where to start?

Scikit-learn has a well-documented toturial on how to start on this [page](http://scikit-learn.org/dev/developers/contributing.html#deprecation). Generally, most of those open-source projects have a contribution guide to help developers to start. Developers can answer queries on **Issue tracker**.  

Since it is my first contribution, I investigated issues with lables `Easy`, `Good first issue`, or `Help wanted`, and then asked for permission of attempt from project maintainers. It is also considered as a good practice to claim the issue by leaving a comment in the pull request to let other developers know you're working on it, hence prevent "competition" from other developers. You don't want people steal your opportunity to contribute, right? 

## Retrieve the latest code and set up the virtual env

It is important to download the **latest** project along with any dependencies and run the entire test suites to make sure that code works before you make any modifications.

1. Fork the main repository on GitHub, and clone my copy to my local disk:
```
$ git clone git@my-github.com:MyLogin/scikit-learn.git
$ cd scikit-learn
$ make clean
```

2. Set up a [virtual environment](https://virtualenv.pypa.io/en/stable/userguide/) and add dependencies. Run the following command in the root level of my project directory.
```
$ virtualenv --no-site-packages ENV --python=python3
$ source ENV/bin/activate
... adding dependencies here ...
```
Read this [page](http://virtualenv.readthedocs.io/en/latest/) on why `virtualenv` is necessary.

3. Launch the test suite by
```
$ make
```
Run the test suite and see where it fails, and make sure it is the same issue as what descirbed in the issue tracker. Then, we can create our an experiment branch and start our code editing.

4. Create a branch to hold my changes:
```
$ git checkout -b my-feature
```
Rule of thumb: **Never works in the master branch**

## Pinpoint where to modify

Now we are ready to inspect reported bugs and edit the source files. However, one may ask "Where can I find those broken code snippets". No worries! Unix/Linux has a powerful tool to help us narrow down the places we need to look at:

```
grep -r -n "your-search-pattern" <start-dir>
```
This command will **recursively**(flag `-r`) search through all the files under `<start-dir>` and find the lines of code matching with `your-search-pattern`. Full file names will be printed out to the console along with **line number**(flag `-n`) after running the command above.

Now I know where to edit, yay! ;)


*Note: Always use `git diff` to see what you've modified. This practive can be very helpful to prevent undesired editing or typo.*

## Coding

Code, code, and code until I'm done ;)

## Test my code

After adding our edits, we need to test our code to check if we see the same errors by running the [regression testing](https://en.wikipedia.org/wiki/Regression_testing). 

- Ran the test suite in the virtual environment and it passed the test
- Additional checking
	1. unitest coverage checking(at least 90%, better 100%)
	```
	$ pip install nose coverage
	$ nosetests --with-coverage path/to/tests_for_package
	```

	2. No pyflakes warnings, check with
	```
	$ pip install pyflakes
	$ pyflakes path/to/module.py
	```

	3. No PEP8 warnings, check with:
	```
	$ pip install pep8
	$ pep8 path/to/module.py
	```

	4. AutoPEP8 can help you fix some of the easy redundant errors:
	```
	$ pip install autopep8
	$ autopep8 path/to/pep8.py
	```

## Create PR and wait for peer's review

After code passed all the tests, we can merge all the changes into `master` branch of our repo by following [this blog](https://help.github.com/articles/creating-a-pull-request-from-a-fork). 

**File detailed infomation on the modifications made by the edit**. Create a new PR to the upstream project. The open-source project maintainers will review your PR, and merge the PR if it is accepted.



## Happy bug fixing!

Here is one interesting [article](https://opensource.guide/how-to-contribute/) to read before you decide to test the water in the open-source community.

#### ------------------EDIT: Update from my PR------------------ 

![MY first PR](https://s3-us-west-1.amazonaws.com/blogassetswenhao/fst-commit/Screenshot+from+2018-06-15+10-25-25.png)
