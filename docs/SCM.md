# SCM
## Source Code Management Strategy
SVN is great. But git is more popular.

SVN or Git is a file system.

A bot will sync the new files from SVN to Git. Developers using Git create Pull Request on the git repositories.
GNU TeXmacs maintainers will review the Pull Request and download the Pull Request as a patch. Once the patch is
fully tested, one of the maintainers will apply the patch to the official SVN repository.

### A Demo
1. The Github user `sadhen` create a [Pull Request](https://github.com/texmacs/collection/pull/6) on [the collection subproject](https://github.com/texmacs/collection)
2. One of the GNU TeXmacs maintainers review the Pull Request and perform the following steps to apply the patch:

```
wget https://github.com/texmacs/collection/pull/6.patch -O /tmp/diff
cd /path/to/texmacs/trunck/src
git apply /tmp/diff
svn commit -m "More tests on string"
```

3. To clarify, a github or gitlab service is not required to generate the `6.patch`.
The file `6.patch` is easily generated by the `git diff` command line.

### The Internals of Git or SVN
+ Git is a file system for blobs.
+ SVN is a file system for diffs.

