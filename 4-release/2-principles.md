!SLIDE
# Release Principles

!SLIDE
# Never, ever release different code with the same version

!SLIDE
# Yank the botched release

    $ gem yank your_gem -v 1.0.0
    $ # edit the version number
    $ gem build your_gem.gemspec
    $ gem push your_gem-1.0.1.gem

!SLIDE
# Adhere to a consistent versioning policy

!SLIDE
# Keep a changelog

!SLIDE
# Immediately bump the version post-release
## 1.0.1 --> 1.0.2.a

