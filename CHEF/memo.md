http://qiita.com/marumaru8228/items/24302bc9812c820bda91
this site resolved that when i try to install knife-solo to my ubuntu,
there is a error like

sudo gem install knife-solo

```
Building native extensions.  This could take a while...
ERROR:  Error installing knife-solo:
    ERROR: Failed to build gem native extension.

/usr/bin/ruby2.1 extconf.rb
mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h

extconf failed, exit code 1

Gem files will remain installed in /var/lib/gems/2.1.0/gems/libyajl2-1.1.0 for inspection.
Results logged to /var/lib/gems/2.1.0/extensions/x86-linux/2.1.0/libyajl2-1.1.0/gem_make.out
```

sudo -apt-get install ruby2.1-dev

