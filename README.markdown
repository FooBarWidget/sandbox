# About RubySpec

RubySpec is a project to write a complete, executable specification for the Ruby programming language. The goal is official recognition and support from all the organizations currently involved in Ruby implementations. These include MatzRuby (including YARV), JRuby, IronRuby, MacRuby, Ruby.NET, MagLev.

There are two main components to this project:

  1. the RubySpec sources
  2. the MSpec framework

The source for both are hosted at Github while the documentation and tickets are hosted here.

This project has a free-flowing commit bit policy. If you have had a patch accepted by any current Ruby implementation project, you can get a commit bit by referencing your patch. Anyone who submits an accepted patch to this project will also receive a commit bit. The only requirement is that you have a Github account.

## Running RubySpec

The RubySpec specification files are written in Ruby, utilizing the [MSpec](http://github.com/rubyspec/mspec/tree/master) testing framework, so you need to download MSpec in order to run the RubySpec suite. If you don't have MSpec yet, then go to a directory outside the RubySpec directory and check out its source code from Github:

    cd /somewhere
    git clone git://github.com/rubyspec/mspec.git
    # MSpec is now available in /some-directory/mspec.

If you already have MSpec, then you should run 'git pull' from the MSpec source directory from time to time, because RubySpec often utilizes the latest MSpec features.

By invoking the MSpec script inside the RubySpec directory, it will run the entire RubySpec suite against the Ruby interpreter (named 'ruby') in your PATH:

    cd /path-to-rubyspec
    /somewhere/mspec/bin/mspec

### Running RubySpec against a specific Ruby interpreter

Use the `-t` option to specify the Ruby interpreter that you want to run RubySpec against. The argument may be a full path to the Ruby binary:

    # Runs RubySpec against /opt/ruby-enterprise/bin/ruby
    /somewhere/mspec/bin/mspec -t /opt/ruby-enterprise/bin/ruby

The argument may also be a shortcut. For example, if you specify `j`, then MSpec will look for 'jruby' in PATH and run RubySpec against that:

    # Runs RubySpec against JRuby in PATH.
    /somewhere/mspec/bin/mspec -t j

See `mspec --help` for a list of possible '-t' shortcut values.