!SLIDE
# Anatomy of a RubyGem #

!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

    timecop/
      bin/
      lib/
      test/
      timecop.gemspec

!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

    timecop/
    
<div class="highlight"><pre><code>  bin/</code> &lt;-- Executables here</pre></div>

      lib/
      test/
      timecop.gemspec
  
      
!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

    timecop/
      bin/
      
<div class="highlight"><pre><code>  lib/</code> &lt;-- Code here</pre></div>

      test/
      timecop.gemspec


!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

    timecop/
      bin/
      lib/
      
<div class="highlight"><pre><code>  test/</code> &lt;-- Tests here</pre></div>

      timecop.gemspec


!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

    timecop/
      bin/
      lib/
      test/

<div class="highlight"><pre><code>  timecop.gemspec</code> &lt;-- Your gemspec</pre></div>

!SLIDE
# Anatomy of a RubyGem #
## Directory Structure

### That's it.

!SLIDE smaller
# The gemspec

    @@@ ruby
    Gem::Specification.new do |s|
      s.name = %q{timecop}
      s.version = "0.3.5"
      s.required_rubygems_version = Gem::Requirement.new(">= 0") if s.respond_to? :required_rubygems_version=
      s.authors = ["John Trupiano"]
      s.date = %q{2009-12-07}
      s.description = %q{A gem providing "time travel" and "time freezing" capabilities, making it dead simple to test time-dependent code.  It provides a unified method to mock Time.now, Date.today, and DateTime.now in a single call.}
      s.email = %q{jtrupiano@gmail.com}
      s.extra_rdoc_files = ["LICENSE", "README.rdoc"]
      s.files = ["History.rdoc", "LICENSE", "README.rdoc", "Rakefile", "VERSION.yml", "lib/timecop.rb", "lib/timecop/time_extensions.rb", "lib/timecop/time_stack_item.rb", "lib/timecop/timecop.rb", "test/run_tests.sh", "test/test_helper.rb", "test/test_time_stack_item.rb", "test/test_timecop.rb", "test/test_timecop_without_date.rb", "test/test_timecop_without_date_but_with_time.rb"]
      s.homepage = %q{http://github.com/jtrupiano/timecop}
      s.rdoc_options = ["--charset=UTF-8"]
      s.require_paths = ["lib"]
      s.rubyforge_project = %q{johntrupiano}
      s.rubygems_version = %q{1.3.5}
      s.summary = %q{A gem providing "time travel" and "time freezing" capabilities, making it dead simple to test time-dependent code.  It provides a unified method to mock Time.now, Date.today, and DateTime.now in a single call.}
      s.test_files = ["test/test_helper.rb","test/test_time_stack_item.rb","test/test_timecop.rb","test/test_timecop_without_date.rb","test/test_timecop_without_date_but_with_time.rb"]
    end
    
!SLIDE
# The gemspec
## It's just Ruby

!SLIDE bullets incremental
# RubyGem Workflows
## Tools

* Jeweler
* Hoe / Echoe
* Bones
* newgem

!SLIDE
# Workflow
## Just pick one and use it regularly