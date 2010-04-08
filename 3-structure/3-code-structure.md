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
    $ irb(main):001:0> new_constants { require 'timecop' }
    => ["Singleton", "Timecop"]
    
!SLIDE commandline incremental
# Don't pollute the global namespace
## v0.2.0

    @@@ ruby
    $ irb(main):001:0> new_constants { gem 'timecop', '= 0.2.0'; require 'timecop' }
    => ["Singleton", "StackItem", "Timecop"]


!SLIDE
# Minimize Dependencies

!SLIDE
# Choose Your Dependencies Wisely

!SLIDE
# Fewer dependencies === Easier for others to use

