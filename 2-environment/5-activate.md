!SLIDE small
# custom_require.rb #

    @@@ ruby
    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then

<div class="highlight"><pre><code>      Gem.activate(spec.name, "= #{spec.version}")</code></pre></div>

    @@@ ruby
          gem_original_require path
        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end

!SLIDE smaller
# Gem#activate

<div class="highlight"><pre><code># Gem#activate adds the library paths in +gem+ to $LOAD_PATH.</code></pre></div>

    @@@ ruby
    # Before a Gem is activated its required Gems are activated.  
    # If the version information is omitted, the highest version 
    # Gem of the supplied name is loaded.  If a Gem is not found 
    # that meets the version requirements or a required Gem is
    # not found, a Gem::LoadError is raised.
    def self.activate(gem, *version_requirements)
    
!SLIDE commandline incremental smaller
# Gem activation and the load path

    $ irb(main):003:0> pp $:
    ["/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby/lib/ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil
    
!SLIDE commandline incremental smaller
# Gem activation and the load path

    $ irb(main):004:0> require 'timecop'
    => true
    $ irb(main):005:0> pp $:
    ["/Users/john/.rubies/ruby/lib/ruby/gems/1.8/gems/timecop-0.3.4/bin",
     "/Users/john/.rubies/ruby/lib/ruby/gems/1.8/gems/timecop-0.3.4/lib",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby/lib/ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil
    
!SLIDE smaller commandline
# Gem activation and the load path

    $ irb(main):004:0> require 'timecop'
    => true
    $ irb(main):005:0> pp $:
<div class="highlight"><pre><code> ["/Users/john/.rubies/ruby/lib/ruby/gems/1.8/gems/timecop-0.3.4/bin",
 "/Users/john/.rubies/ruby/lib/ruby/gems/1.8/gems/timecop-0.3.4/lib",</pre></code></div>
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby/lib/ruby/1.8",
     "/Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil


!SLIDE small
# custom_require.rb #

    @@@ ruby
    module Kernel
      alias gem_original_require require

      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")

<div class="highlight"><pre><code>      gem_original_require path</code></pre></div>

    @@@ ruby
        else
          raise load_error
        end
      end

      private :require
      private :gem_original_require
    end

!SLIDE
# So...
## RubyGems is just managing your load path
