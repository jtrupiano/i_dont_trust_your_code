!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then

<div class="highlight"><pre><code>      Gem.activate(spec.name, "= #{spec.version}")</code></pre></div>

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

    # Before a Gem is activated its required Gems are activated.  
    # If the version information is omitted, the highest version 
    # Gem of the supplied name is loaded.  If a Gem is not found 
    # that meets the version requirements or a required Gem is
    # not found, a Gem::LoadError is raised.
    def self.activate(gem, *version_requirements)
    
!SLIDE commandline incremental smaller
# Gem activation and the load path

    $ irb(main):003:0> pp $:
    ["/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/bin",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/lib",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil
    
!SLIDE commandline incremental smaller
# Gem activation and the load path

    $ irb(main):004:0> require 'timecop'
    => true
    $ irb(main):005:0> pp $:
    ["/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/bin",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/lib",
     "/Users/john/.gem/ruby/1.8/gems/timecop-0.3.4/bin",
     "/Users/john/.gem/ruby/1.8/gems/timecop-0.3.4/lib",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil
    
!SLIDE commandline smaller
# Gem activation and the load path

    $ irb(main):004:0> require 'timecop'
    => true
    $ irb(main):005:0> pp $:
    ["/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/bin",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/gems/1.8/gems/open_gem-1.4.0/lib",

<div class="highlight"><pre><code> "/Users/john/.gem/ruby/1.8/gems/timecop-0.3.4/bin",
 "/Users/john/.gem/ruby/1.8/gems/timecop-0.3.4/lib",</pre></code></div>

     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby/1.8/i686-darwin9.8.0",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/site_ruby",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8",
     "/Users/john/.rubies/ruby-enterprise-1.8.6-20090610/lib/ruby/1.8/i686-darwin9.8.0",
     "."]
    => nil

