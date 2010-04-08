!SLIDE
# Code Structure #

!SLIDE
# Minimize Your Footprint
## House everything under a single module
### timecop ==> Timecop

!SLIDE
# Don't pollute the global namespace

    @@@ ruby
    # Shows you which top-level constants have been added
    # Usage: new_constants { require 'timecop' }
    def new_constants(&block)
      constants = Object.constants
      yield
      (Object.constants - constants).sort
    end

!SLIDE commandline incremental
# Don't pollute the global namespace
## v0.3.4

    @@@ ruby
    $ irb> new_constants { require 'timecop' }
    => ["Singleton", "Timecop"]
    
!SLIDE commandline incremental
# Don't pollute the global namespace
## v0.2.0

    @@@ ruby
    $ irb> gem 'timecop', '= 0.2.0'
    => true
    $ irb> new_constants { require 'timecop' }
    => ["Singleton", "StackItem", "Timecop"]

