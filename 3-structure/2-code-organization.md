!SLIDE
# Code Organization #

!SLIDE bullets
# Directory "Namespacing"
* A single file named the *exact same thing* as your gem
* A single directory named the *exact same thing* as your gem (if necessary)

!SLIDE
# Directory "Namespacing"

    lib/
      timecop/
      timecop.rb
      
!SLIDE
# Directory "Namespacing"
## Why?

!SLIDE small
# Gem.searcher.find(path) #

    @@@ ruby
    class Gem::GemPathSearcher
      def find(path)
        @gemspecs.find do |spec| matching_file? spec, path end
      end
 
      def init_gemspecs
        specs = Gem.source_index.map { |_, spec| spec }

<pre><code> </code></pre>
<div class="highlight"><pre><code>    specs.sort { |a, b|</code></pre></div>
<div class="highlight"><pre><code>      names = a.name &lt;=> b.name</code></pre></div>

    @@@ ruby
          next names if names.nonzero?
          b.version <=> a.version
        }
      end
    end

!SLIDE
# Directory "Namespacing"
## Two gems, gem1 and gem2.

    gem1/
      lib/
        gem1.rb
        gem2.rb
        
    gem2/
      lib/
        gem2.rb

!SLIDE commandline incremental
# Directory "Namespacing"

    @@@ ruby
    $ irb(main):001:0> require 'gem2'
    => true
    $ irb(main):002:0> Gem.loaded_specs.keys.grep("gem2")
    => []
    $ irb(main):003:0> Gem.loaded_specs.keys.grep("gem1")
    => ["gem1"]
    