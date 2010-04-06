!SLIDE small
# Gem.searcher.find(path) #

    class Gem::GemPathSearcher
      def find(path)
        @gemspecs.find do |spec| matching_file? spec, path end
      end
            
      def init_gemspecs
        specs = Gem.source_index.map { |_, spec| spec }

        specs.sort { |a, b|
          names = a.name <=> b.name
          next names if names.nonzero?
          b.version <=> a.version
        }
      end
    end
    
!SLIDE small
# Gem.searcher.find(path) #

    class Gem::GemPathSearcher

<div class="highlight"><pre><code>  def find(path)
    @gemspecs.find do |spec| matching_file? spec, path end
  end
</code></pre></div>
<pre><code> </code></pre>
 
      def init_gemspecs
        specs = Gem.source_index.map { |_, spec| spec }
 
        specs.sort { |a, b|
          names = a.name <=> b.name
          next names if names.nonzero?
          b.version <=> a.version
        }
      end
    end

!SLIDE small
# Gem.searcher.find(path) #

    class Gem::GemPathSearcher
      def find(path)
        @gemspecs.find do |spec| matching_file? spec, path end
      end
 
<pre><code> </code></pre>
<div class="highlight"><pre><code>  def init_gemspecs</code></pre></div>

        specs = Gem.source_index.map { |_, spec| spec }
 
        specs.sort { |a, b|
          names = a.name <=> b.name
          next names if names.nonzero?
          b.version <=> a.version
        }
      end
    end

!SLIDE small
# Gem.searcher.find(path) #

    class Gem::GemPathSearcher
      def find(path)
        @gemspecs.find do |spec| matching_file? spec, path end
      end
 
      def init_gemspecs
        specs = Gem.source_index.map { |_, spec| spec }

<pre><code> </code></pre>
<div class="highlight"><pre><code>    specs.sort { |a, b|</code></pre></div>
<div class="highlight"><pre><code>      names = a.name &lt;=> b.name</code></pre></div>

          next names if names.nonzero?
          b.version <=> a.version
        }
      end
    end

