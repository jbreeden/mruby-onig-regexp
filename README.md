# mruby-onig-regexp

## install by mrbgems
```ruby
MRuby::Build.new do |conf|

    # ... (snip) ...

    conf.gem :github => 'mattn/mruby-onig-regexp'
end
```

## Example
```ruby

def matchstr(str)
  reg = Regexp.compile("abc")

  if reg =~ str then
    p "match"
  else
    p "not match"
  end
end

matchstr("abcdef") # => match
matchstr("ghijkl") # => not match
matchstr("xyzabc") # => match
```

## Building on Windows

By default, libonig will be downloaded and built while building mruby when using this mrbgem. These build steps involve running unix utilities and shell scripts, and won't typically work on Windows. As a workaround, you can download [libonig](http://www.geocities.jp/kosako3/oniguruma/archive/onig-5.9.5.tar.gz) and build it yourself (e.g. with mingw). Then just set the ONIG_HOME environment variable to the directory where you extracted libonig before making mruby.
