!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require

      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")
          gem_original_require path
        else
          raise load_error
        end
      end

      private :require
      private :gem_original_require
    end

!SLIDE small
# custom_require.rb #

    module Kernel
    
<div class="highlight"><pre><code>  alias gem_original_require require</code></pre></div>
<pre><code> </code></pre>
       
      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")
          gem_original_require path
        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end

!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
      
<div class="highlight"><pre><code>    gem_original_require path</code></pre></div>

      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")
          gem_original_require path
        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end

!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
        gem_original_require path

<div class="highlight"><pre><code>  rescue LoadError => load_error</code></pre></div>

        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")
          gem_original_require path
        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end

!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and

<div class="highlight"><pre><code>       spec = Gem.searcher.find(path) then</code></pre></div>

          Gem.activate(spec.name, "= #{spec.version}")
          gem_original_require path
        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end

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

!SLIDE small
# custom_require.rb #

    module Kernel
      alias gem_original_require require
 
      def require(path) # :doc:
        gem_original_require path
      rescue LoadError => load_error
        if load_error.message =~ /#{Regexp.escape path}\z/ and
           spec = Gem.searcher.find(path) then
          Gem.activate(spec.name, "= #{spec.version}")

<div class="highlight"><pre><code>      gem_original_require path</code></pre></div>

        else
          raise load_error
        end
      end
 
      private :require
      private :gem_original_require
    end
