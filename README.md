# qtlocation-debian
https://salsa.debian.org/qt-kde-team/qt/qtlocation.git

# Build
- Use the following commands to download the upstream
  ```
  $ git clone git@github.com:qt/qtlocation.git -b [tag name] --single-branch --depth=1
  $ cd qtlocation
  $ git submodule update --init
  ```
- Copy the `./debian` directory to the upstream `qtlocation` directory
- go to the the upstream `qtlocation` directory abd build the package:

  ```
  $ mk-build-deps -Pnodoc -s sudo -i
  ## parallel=n: built using up to n parallel processes, n must be a integer
  $ export DEB_BUILD_OPTIONS="parallel=n nocheck"
  $ dpkg-buildpackage -b --no-sign -Pnodoc
  ```
