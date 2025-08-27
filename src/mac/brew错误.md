brew异常
```shell
yunhai@bogon Downloads % brew
Traceback (most recent call last):
        11: from /usr/local/Homebrew/Library/Homebrew/brew.rb:13:in `<main>'
        10: from /usr/local/Homebrew/Library/Homebrew/brew.rb:13:in `require_relative'
         9: from /usr/local/Homebrew/Library/Homebrew/global.rb:26:in `<top (required)>'
         8: from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
         7: from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
         6: from /usr/local/Homebrew/Library/Homebrew/os.rb:1:in `<top (required)>'
         5: from /usr/local/Homebrew/Library/Homebrew/os.rb:19:in `<module:OS>'
         4: from /usr/local/Homebrew/Library/Homebrew/os/mac.rb:52:in `prerelease?'
         3: from /usr/local/Homebrew/Library/Homebrew/os/mac.rb:18:in `version'
         2: from /usr/local/Homebrew/Library/Homebrew/os/mac.rb:18:in `new'
         1: from /usr/local/Homebrew/Library/Homebrew/os/mac/version.rb:29:in `initialize'
/usr/local/Homebrew/Library/Homebrew/version.rb:369:in `initialize': Version value must be a string; got a NilClass () (TypeError)
```
重置试试：
> yunhai@bogon Downloads % brew update-reset

