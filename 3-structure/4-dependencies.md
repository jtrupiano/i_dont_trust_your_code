!SLIDE
# Minimize Dependencies

!SLIDE
# Choose Your Dependencies Wisely

!SLIDE
# Fewer dependencies === Easier for others to use

!SLIDE
# Pessimistic Dependencies
## ~> 
### Great in theory, but not often in practice

!SLIDE small
# Distinguish Between Runtime and Development Dependencies

    @@@ ruby
    Gem::Specification.new do |s|
      s.name = %q{rack-rewrite}
      s.version = "0.2.1"
      # ...
      s.add_dependency(%q<rack>, [">= 1.0"])
      s.add_development_dependency(%q<shoulda>, [">= 2.10.3"])
    end
    
!SLIDE
# Development Dependencies
## Your gem does not have a runtime dependency on gemcutter, jeweler, hoe, etc.

