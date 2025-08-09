# Chubby
Work Locally, Edit Remotely!

> Dedicated to James Chubbuck, who refuses to use Vim because he doesn't want
> to use it over ssh.

## Usage
chubby [-t timer] [-O legacy_scp] [-r recursive] [-B batch_mode] [-p port] 
       [-D pre_delete] src dest

src and dest are the source file(s) and destination file or directory. Either
can be via ssh (john@example.com:/path/to/file/or/directory) or locally
(/path/to/file/or/directory). 

-t: A positive integral value, representing how many seconds the program waits
    before updating the destination again. Set to 0 to manually continue in
    between each update. Defaults to 0.

-O: Use the legacy SCP protocol for file transfers instead of the SFTP 
    protocol. Forcing the use of the SCP protocol may be necessary for servers 
    that do not implement SFTP, for backwards-compatibility for particular 
    filename wildcard patterns and for expanding paths with a ‘~’ prefix for 
    older SFTP servers.

-r: Recursively copy entire directories.

-B: Selects batch mode (prevents asking for passwords or passphrases).

-p: Specifies the port to connect to on the remote host if SSH is being used.
    May be written with a lowercase or capital P.

-D: Enables Pre-Delete, which first deletes the file or directory at the
    destination before copying the source. Note that if you are recursively
    copying a directory, this can be potentially destructive and delete files
    that were not intended to be deleted.
