# APKBUILD penguins-eggs

# install alpine-sdk
apk add alpine-sdk

# user executing abuild member of the abuild group.

adduser artisan abuild

# create keys
```
abuild-keygen -n
```

Insert on `~/.abuild/abuild.conf`:
```
PACKAGER_PRIVKEY="/home/artisan/.abuild/piero.proietti@gmail.com-66b8815d.rsa"
```

Copia della chiave in /etc/apk/keys
```
doas cp /home/artisan/.abuild/piero.proietti@gmail.com-68412146.rsa /etc/apk/keys
```

abuild Commands:
* `build`       Compile and install package into $pkgdir
* `check`       Run any defined tests concerning the package
* `checksum`    Generate checksum to be included in APKBUILD
* `clean`       Remove temp build and install dirs
* `cleancache`  Remove downloaded files from $SRCDEST
* `cleanoldpkg` Remove binary packages except current version
* `cleanpkg`    Remove already built binary and source package
* `deps`        Install packages listed in makedepends and depends
* `fetch`       Fetch sources to $SRCDEST (consider: 'abuild fetch verify')
* `index`       Regenerate indexes in $REPODEST
* `listpkg`     List target packages
* `package`     Install project into $pkgdir
* `prepare`     Apply patches
* `rootbld`     Build package in clean chroot
* `rootpkg`     Run 'package', the split functions and create apks as fakeroot
* `sanitycheck` Basic sanity check of APKBUILD
* `snapshot`    Create a $giturl snapshot and upload to $disturl
* `sourcecheck` Check if remote source package exists upstream
* `srcpkg`      Make a source package
* `undeps`      Uninstall packages listed in makedepends and depends
* `unpack`      Unpack sources to $srcdir
* `up2date`     Compare target and sources dates
* `verify`      Verify checksums
