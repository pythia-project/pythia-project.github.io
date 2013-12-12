---
layout: docs
title: Development environment
toctitle: Environment
---

Before you start hacking on Pythia, let us take a few moments to set up your
environment.
As Pythia makes use of User-mode Linux, the development environment is required
to run on a Linux kernel too.

The following prerequisites are also needed:
* [Go][] 1.1 or later
* [GNU Make][]
* A 32-bit C toolchain
* [Squashfs][] tools 4.2 or later
* wget

[Go]: http://golang.org/
[GNU Make]: http://www.gnu.org/software/make/
[Squashfs]: http://squashfs.sourceforge.net/


## Getting the code

The canonical repository is located at <{{ site.repository }}>.
You can get a local clone with

{% highlight bash %}
git clone {{ site.repository }}.git
{% endhighlight %}

Once your clone is set up, go inside the new directory and run

{% highlight bash %}
devtools/gitsetup.sh
{% endhighlight %}

This will install some git hooks to check the code style before a commit.
If you wish to use your own custom hooks, add the `.local` suffix to the hook
name.


## Building

Pythia uses GNU Make as its build system.
To build the whole platform, simply run `make` from the root of the source tree.
The result is available in the `out` directory.

More commands are available.
You can get a list of them by running `make help`.


## Working with Go

To set up a shell session for working with the go tools, run the following
command from the root of the source tree:

{% highlight bash %}
. devtools/goenvsetup.sh
{% endhighlight %}

This command will set up the `GOPATH` environment variable as well as others
needed for running the unit tests.
It will also launch a `godoc` HTTP server listening on `localhost:6060`.
