= TURN - Test::Unit Reporter (New)
    by Tim Pease
    http://codeforpeople.rubyforge.org/turn

== DESCRIPTION:

TURN is a new way to view Test::Unit results. With longer running tests, it
can be very frustrating to see a failure (....F...) and then have to wait till
all the tests finish before you can see what the exact failure was. TURN
displays each test on a separate line with failures being displayed
immediately instead of at the end of the tests.
  
If you have the 'facets' gem installed, then TURN output will be displayed in
wonderful technicolor (but only if your terminal supports ANSI color codes).
Well, the only colors are green and red, but that is still color.

== FEATURES:

General usage provides better test output. Here is some sample output:

  TestMyClass
      test_alt                                                            PASS
      test_alt_eq                                                         PASS
      test_bad                                                            FAIL
          ./test/test_my_class.rb:64:in `test_bad'
          <false> is not true.
      test_foo                                                            PASS
      test_foo_eq                                                         PASS
  TestYourClass
      test_method_a                                                       PASS
      test_method_b                                                       PASS
      test_method_c                                                       PASS
  ============================================================================
    pass: 7,  fail: 1,  error: 0
    total: 15 tests with 42 assertions in 0.018 seconds
  ============================================================================

Turn also provides solo and cross test modes when run from the *turn* commandline
application.

== SYNOPSIS:

If you have the 'facets' gem installed, then TURN output will be displayed in
wonderful technicolor (but only if your terminal supports ANSI color codes).
Well, the only colors are green and red, but that is still color.

Note that the 'facets' gem is also required if you wish to use the
progressbar output mode.

=== Command Line

You can use the *turn* executable in place of the *ruby* interpreter.

  turn -Ilib test/test_all.rb

This will invoke the ruby interpreter and automatically require the turn
formatting library. All command line arguments are passed "as is" to the
ruby interpreter.

To use the solo runner.

  turn --solo -Ilib test/

This will run all tests in the test/ directory in a separate process.
Likewise for the cross runner.

  turn --cross -Ilib test/

This will run every pairing of tests in a separate process.

=== Require

Simply require the TURN package from within your test suite.

  require 'turn'

This will configure Test::Unit to use TURN formatting for displaying test
restuls. A better line to use, though, is the following:

  begin; require 'turn'; rescue LoadError; end

When you distribute your code, the test suite can be run without requiring
the end user to install the TURN package.

For a Rails application, put the require line into the 'test/test_helper.rb'
scipt. Now your Rails tests will use TURN formatting.

== REQUIREMENTS:

* facets 2.0+ (for colorized output and progressbar output mode)

== INSTALL:

* sudo gem install turn

== LICENSE:

MIT License

Copyright (c) 2006-2008

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

