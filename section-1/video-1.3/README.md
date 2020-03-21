# Video 1.3

In this video we will install `jx`, the Jenkins X command line tool.

## Installing

Start by visiting this link:

https://jenkins-x.io/docs/getting-started/setup/install/

There are download instructions for macOS, Linux, and Windows.

## Linux PATH

For the Linux installation, we need to make sure that `jx` is on the PATH.
I recommend creating a directory `$HOME/bin` as this will allow updating
`jx` as a normal user.

To create the directory and move `jx` there:

```
mkdir -p $HOME/bin
mv jx $HOME/bin
```

In many cases, the `$HOME/bin` directory will already be on the PATH. If not,
add this line to `$HOME/.bashrc` or `$HOME/.bash_profile`, as applicable:

```
export PATH="$HOME/bin:${PATH}"
```

## Verifying Install

To verify that `jx` is installed correctly and check the version, run:

```
jx --version
```
