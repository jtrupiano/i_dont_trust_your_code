!SLIDE
# require 'rubygems' #

!SLIDE
# require 'rubygems' #

## Hijacks `Kernel#require`


!SLIDE
# require 'rubygems' #

## You've seen the stacktraces


!SLIDE incremental commandline
# require 'rubygems' #

    $ irb(main):002:0> require 'foo'
    LoadError: no such file to load -- foo
      from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
        /rubygems/custom_require.rb:31:in `gem_original_require'
      from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
        /rubygems/custom_require.rb:31:in `require'
      from (irb):2

!SLIDE commandline
# require 'rubygems' #

<div>
<pre><code class="command">$ irb(main):002:0> require 'foo'</code></pre>
<div class="highlight"><pre><code class="result">LoadError: no such file to load -- foo</code></pre></div>
<pre><code class="result">  from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
    /rubygems/custom_require.rb:31:in `gem_original_require'
  from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
    /rubygems/custom_require.rb:31:in `require'
  from (irb):2
</code></pre>
</div>

!SLIDE commandline
# require 'rubygems' #

<div>
<pre>
<code class="command">$ irb(main):002:0> require 'foo'</code>
<code class="result">LoadError: no such file to load -- foo
  from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8</code>
</pre>
<div class="highlight"><pre><code class="result">    /rubygems/custom_require.rb:31:in `gem_original_require'</code></pre></div>
<pre>
<code class="result">  from /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8</code>
</pre>
<div class="highlight"><pre><code class="result">    /rubygems/custom_require.rb:31:in `require'</code></pre></div>
<pre><code class="result">  from (irb):2</code></pre>
</div>
