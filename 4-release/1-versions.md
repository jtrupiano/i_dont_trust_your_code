!SLIDE
# Releases

!SLIDE
# Versioning

!SLIDES bullets incremental
# Basics
* number of segments is actually infinite (1.2.3.4.5.6.7.8 is perfectly valid)
* 1.2 == 1.2.0.0.0.0.0.0.0.0.0...
* alphanumeric sort, a < 0
* 1.2.a < 1.2 < 1.2.1.a < 1.2.1

!SLIDE
# Versioning ~ Religion
## These are my thoughts, not necessarily generally accepted

!SLIDE
# 1.2.3.a
## major.minor.patch.build

!SLIDE bullets incremental
# 1.0 means stable
* It's an indication to the community that you deem the library ready for public use.
* It defines an API that won't break without a good reason (and another major version bump)

!SLIDE bullets incremental
# Patch version bumps
* Introduce deprecation warnings
* Introduce new functionality
* Fix bugs or other documentation

!SLIDE bullets incremental
# Minor version bumps 
* Break planned and communicated backwards-compatibility
* Eliminate deprecation notices in the previous minor version
* Introduce new functionality

!SLIDE bullets incremental
# Major version bumps 
* Break backwards-compatibility
* Often include rewrite of large parts of the code
* Introduce new functionality

!SLIDE
# Prereleases

!SLIDE
# Prereleases
## Identified by the presence of an alphabet character in the version number

!SLIDE bullets incremental
# Prereleases
## Use as appropriate
* Introducing a new feature you're not 100% comfortable with
* Reimplementing an existing feature
* Don't have access to all environments (Windows)

