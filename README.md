Slop: Ruby bug squash
====

Slop is a command line option parsing library.

Your goal is to find the root cause of the bug described below, then fix it if you have time - happy coding!

## The bug

When a negative number is passed in as a command line argument, it is not being parsed correctly:

```
@options = Slop::Options.new
@options.integer "--port"
@parser = Slop::Parser.new(@options)
@result = @parser.parse %w(--port=-123)
puts @result[:port]
```

Actual:
```
nil
```

Expected:
```
-123
```

## Requirements & set up

- Ruby - Any recent version should be good

Install the dependencies:
```
bundle install
```

## Running the tests

To run the entire test suite:
```
rake test
```

To run a single test file:
```
rake test TEST=test/error_test.rb
```

To run all tests which match a regular expression across all files:
```
rake test TESTOPTS="--name='/raises when/'"
```

To run a specific test in a specific file (technically this would run all matching tests in the file):
```
rake test TEST=test/error_test.rb TESTOPTS="--name='/raises when an argument is missing/'"
```

---

The [original readme](README_ORIGINAL.md) contains overall documentation about the project.  It can be
used as a source of information if you find you need it.

---
