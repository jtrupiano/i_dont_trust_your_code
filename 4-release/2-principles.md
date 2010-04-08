!SLIDE
# Release Principles

!SLIDE
# Never, ever release different code with the same version

!SLIDE
# Yank the botched release

    $ gem yank your_gem -v 1.0.0
    $ rake version:bump:patch 
    $ rake build
    $ gem push your_gem-1.0.1.gem

!SLIDE
# Post-release

!SLIDE
# Immediately bump the version
## 1.0.1 --> 1.0.2.a

