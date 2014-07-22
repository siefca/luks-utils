luks-utils v 1.3
===================

A set of POSIX shell scripts for making LUKS management easier.

## luks-mount-interactive

This script interactively asks for a passphrase of an encrypted volume, unlocks it and then tries to mount it.

### Examples

Displaying usage:

* `luks-mount-interactive --help`

Mounting an encrypted partition which path and map name is in `/etc/crypttab` and mount point is in `/etc/fstab`:

* `luks-mount-interactive cryptdocs`

Mounting an encrypted partition that has no given mount point in `/etc/fstab` or the mount point should be different:

* `luks-mount-interactive cryptdocs /mnt/secret_docs`

Mounting an encrypted partition that also has no entry in `/etc/crypttab`:

* `luks-mount-interactive /dev/sdd1 /mnt/secret_docs cryptdocs` (first partition of `sdd`)
* `luks-mount-interactive /dev/md/docs /mnt/secret_docs cryptdocs` (MD device labeled `docs`)

Running as a user (uses `sudo` or `gksudo`):

* `luks-mount-interactive --sudo cryptdocs`

Debugging:

* `luks-mount-interactive --debug cryptdocs`

Using encrypted drive only to authenticate in some other script (no unlocking, no mounting):

* `luks-mount-interactive --check-password cryptodocs`
* `luks-mount-interactive --check-password /dev/sdd1`

## luks-headers-backup
## luks-determine-device

## Installation

Copy scripts to `/usr/local/sbin` or to `/usr/sbin`.

