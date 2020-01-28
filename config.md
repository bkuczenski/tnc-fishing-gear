# Configuration Information

This is just kind of a lazy log of steps I have taken to configure the repo and my work.


## Installing FishStatJ

This necessitated installing a specific version of the Java Dev Kit specified in the docs:

JDK 1.8: oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

I validated its correct installation by running the following:

    $ /usr/libexec/java_home -V
    Matching Java Virtual Machines (1):
    1.8.0_241, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_241.jdk/Contents/Home
    
    /Library/Java/JavaVirtualMachines/jdk1.8.0_241.jdk/Contents/Home

## Installing Python

Python is my tool of choice for data hacking.  I recently learned `pipenv` is the hot new easy replacement for `pip` + `virtualenv` + `virtualenvwrapper`, which was a system that was not really working for me.

I followed the instructions here: https://docs.python-guide.org/starting/install3/osx/

Essentially:

 * `gcc` was already installed, but I had remembered this command from before so I ran it:

    $ xcode-select --install

 * Homebrew came next:

    $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

 * The path seemed to already contain `/usr/local/bin` so I simply:

    $ brew install python

   which informed me that binaries were installed in `/usr/local/opt/python/libexec/bin/`. So I created a `.bash_profile` and included "export PATH=/usr/local/opt/python/libexec/bin:${PATH}" in that file.  Then

    $ which pip
    /usr/local/opt/python/libexec/bin/pip
    $ pip install pipenv

   Reading more, I've decided pipenv does not work for me. So I will stick with pip and virtualenv.

    $ pip uninstall pipenv
    $ pip install virtualenvwrapper

   Go back to `.bash_profile` and add the following:

    source /usr/local/bin/virtualenvwrapper.sh

   Now back to reality..

    $ mkvirtualenv tnc-aldfg

   And we're rock and rolling.

