!SLIDE incremental bullets
# RubyGems != Ruby #

!SLIDE commandline incremental smaller
# The Ruby Load Path #

    $ ~/playground $> irb -f
    $ irb(main):001:0> puts $:
    /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
    /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0
    /Users/john/.rubies/ruby/lib/ruby/site_ruby
    /Users/john/.rubies/ruby/lib/ruby/1.8
    /Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0
    .
    => nil
    
!SLIDE smaller
# The Ruby Load Path #

<div class="smaller">
<pre><code>$ ~/playground $&gt; irb -f
$ irb(main):001:0&gt; puts $:
/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0
/Users/john/.rubies/ruby/lib/ruby/site_ruby
<code class="highlight">/Users/john/.rubies/ruby/lib/ruby/1.8</code>
/Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0
.
=&gt; nil</code></pre>
</div>

!SLIDE commandline incremental smaller
# The Ruby Load Path #
    $ ~/playground $> ls /Users/john/.rubies/ruby/lib/ruby/1.8/
    
    English.rb        erb.rb            mathn.rb          profiler.rb       sync.rb
    Env.rb            eregex.rb         matrix.rb         pstore.rb         tempfile.rb
    abbrev.rb         expect.rb         md5.rb            racc              test
    base64.rb         fileutils.rb      mkmf.rb           rational.rb       thread.rb
    benchmark.rb      finalize.rb       monitor.rb        rdoc              thwait.rb
    bigdecimal        find.rb           mutex_m.rb        readbytes.rb      time.rb
    cgi               forwardable.rb    net               resolv-replace.rb timeout.rb
    cgi-lib.rb        ftools.rb         observer.rb       resolv.rb         tmpdir.rb
    cgi.rb            generator.rb      open-uri.rb       rexml             tracer.rb
    complex.rb        getoptlong.rb     open3.rb          rinda             tsort.rb
    csv.rb            getopts.rb        openssl           rss               un.rb
    date              gserver.rb        openssl.rb        rss.rb            uri
    date.rb           i686-darwin9.8.0  optparse          rubyunit.rb       uri.rb
    date2.rb          importenv.rb      optparse.rb       runit             weakref.rb
    debug.rb          io                ostruct.rb        scanf.rb          webrick
    delegate.rb       ipaddr.rb         parsearg.rb       set.rb            webrick.rb
    digest            irb               parsedate.rb      sha1.rb           wsdl
    digest.rb         irb.rb            pathname.rb       shell             xmlrpc
    dl                jcode.rb          ping.rb           shell.rb          xsd
    drb               kconv.rb          pp.rb             shellwords.rb     yaml
    drb.rb            logger.rb         prettyprint.rb    singleton.rb      yaml.rb
    e2mmap.rb         mailread.rb       profile.rb        soap

!SLIDE smaller
# The Ruby Load Path
<div class="smaller">
<pre><code>$ ~/playground $> ls /Users/john/.rubies/ruby/lib/ruby/1.8/
  
English.rb        <code class="highlight">erb.rb</code>            mathn.rb          profiler.rb       sync.rb
Env.rb            eregex.rb         matrix.rb         pstore.rb         tempfile.rb
abbrev.rb         expect.rb         md5.rb            racc              test
base64.rb         fileutils.rb      mkmf.rb           rational.rb       <code class="highlight">thread.rb</code>
benchmark.rb      finalize.rb       monitor.rb        rdoc              thwait.rb
bigdecimal        find.rb           mutex_m.rb        readbytes.rb      time.rb
cgi               forwardable.rb    net               resolv-replace.rb timeout.rb
cgi-lib.rb        ftools.rb         observer.rb       resolv.rb         tmpdir.rb
cgi.rb            generator.rb      open-uri.rb       rexml             tracer.rb
complex.rb        getoptlong.rb     open3.rb          rinda             tsort.rb
<code class="highlight">csv.rb</code>            getopts.rb        openssl           rss               un.rb
date              gserver.rb        openssl.rb        rss.rb            uri
<code class="highlight">date.rb</code>           i686-darwin9.8.0  optparse          rubyunit.rb       uri.rb
date2.rb          importenv.rb      optparse.rb       runit             weakref.rb
debug.rb          io                ostruct.rb        scanf.rb          webrick
delegate.rb       ipaddr.rb         parsearg.rb       set.rb            webrick.rb
digest            irb               parsedate.rb      sha1.rb           wsdl
digest.rb         <code class="highlight">irb.rb</code>            pathname.rb       shell             xmlrpc
dl                jcode.rb          ping.rb           shell.rb          xsd
drb               kconv.rb          <code class="highlight">pp.rb</code>             shellwords.rb     yaml
drb.rb            logger.rb         prettyprint.rb    singleton.rb      <code class="highlight">yaml.rb</code>
e2mmap.rb         mailread.rb       profile.rb        soap</code></pre>
</div>


!SLIDE smaller
# The Ruby Load Path #

<div class="smaller">
<pre><code>$ ~/playground $&gt; irb -f
$ irb(main):001:0&gt; puts $:
<code class="highlight">/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8</code>
/Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8/i686-darwin9.8.0
/Users/john/.rubies/ruby/lib/ruby/site_ruby
/Users/john/.rubies/ruby/lib/ruby/1.8
/Users/john/.rubies/ruby/lib/ruby/1.8/i686-darwin9.8.0
.
=&gt; nil</code></pre>
</div>

!SLIDE commandline incremental smaller
# The Ruby Load Path #
    $ ~/playground $> ls /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8
    
    gauntlet_rubygems.rb rbconfig             rubygems.rb
    i686-darwin9.8.0     rubygems             ubygems.rb

!SLIDE smaller
# The Ruby Load Path #
<div class="smaller">
<pre><code>$ ~/playground $> ls /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8

gauntlet_rubygems.rb rbconfig             <code class="highlight">rubygems.rb</code>
i686-darwin9.8.0     rubygems             ubygems.rb</code></pre>
</div>

!SLIDE smaller
# The Ruby Load Path #
<div class="smaller">
<pre><code>$ ~/playground $> ls /Users/john/.rubies/ruby/lib/ruby/site_ruby/1.8

gauntlet_rubygems.rb rbconfig             rubygems.rb
i686-darwin9.8.0     rubygems             <code class="highlight">ubygems.rb</code></code></pre>
</div>


!SLIDE incremental commandline
# What is ubygems.rb? #

    @@@ ruby
    $ cat ubygems.rb
    # This file allows for the running of rubygems with a nice
    # command line look-and-feel: ruby -rubygems foo.rb
    #--
    # Copyright 2006 by Chad Fowler, Rich Kilmer, Jim Weirich 
    # and others. All rights reserved.
    # See LICENSE.txt for permissions.
    #++

    require 'rubygems'

!SLIDE
# What is ubygems.rb? #

## require -rubygems