# Chubby
Work Locally, Edit Remotely!

> Dedicated to James Chubbuck, who refuses to use Vim because it's annoying
> to use it over ssh.

Watch [this video](https://youtu.be/QOWwz68JaNU?si=iXZ76Cb4KYkja1Qe)
for an explanation.

Chubby is a wrapper around scp that aids in the process of editing
files locally and sending them to a remote server. This can be useful
if testing or deployment needs to be done on the remote server, but
you don't want to commit all of your small tweaks onto Git.

## Installation
Download [chubby](https://raw.githubusercontent.com/Kolin63/chubby/refs/heads/main/chubby),
give it execute permissions, and put it somewhere that's in your path (like
`/usr/bin`. Or, you can run this installation script:
```
sudo wget https://github.com/Kolin63/chubby/raw/refs/heads/main/chubby -O /usr/bin/chubby
sudo chmod +x /usr/bin/chubby
```

## Using Chubby
Start by making a file named .chubby in the root directory of your
project. In the file, use the syntax of `[args] src dest`. An
example line would be: `-rO src/ john@example.com:~/project/src/`
Note that Chubby Files are line based, so make sure to put one
operation on a line.

Now that the .chubby file is made, you can run the command `chubby` in
any sub-directory and that file will be executed.

Since Chubby is an scp wrapper, any arguments not listed below will be
passed to scp. Therefore, any and all scp arguments are valid for
Chubby to use. For the same reason, Chubby can copy files on the same
machine, over an SSH connection, or over an SCP connection (scp://)
