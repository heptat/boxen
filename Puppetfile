# This file manages Puppet module dependencies.
#
# It works a lot like Bundler. We provide some core modules by
# default. This ensures at least the ability to construct a basic
# environment.

# Shortcut for a module from GitHub's boxen organization
def github(name, *args)
  options ||= if args.last.is_a? Hash
    args.last
  else
    {}
  end

  if path = options.delete(:path)
    mod name, :path => path
  else
    version = args.first
    options[:repo] ||= "boxen/puppet-#{name}"
    mod name, version, :github_tarball => options[:repo]
  end
end

# Shortcut for a module under development
def dev(name, *args)
  mod name, :path => "#{ENV['HOME']}/src/boxen/puppet-#{name}"
end

# Includes many of our custom types and providers, as well as global
# config. Required.

github "boxen", "3.3.5"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "git",        "1.3.7"
github "nginx",      "1.4.3"
github "homebrew",   "1.6.0"
github "gcc",        "2.0.1"
github "openssl",    "1.0.0"
github "pkgconfig",  "1.0.0"
github "ruby",       "6.7.6"
github "stdlib",     "4.1.0", :repo => "puppetlabs/puppetlabs-stdlib"
github "repository", "2.2.0"
github "redis",      "2.1.0"
github "mysql",      "1.2.0"
github "vim",        "1.0.5"

# not sure about these:
# github "inifile",    "1.0.0", :repo => "puppetlabs/puppetlabs-inifile"
# github "sudo",       "1.0.0"

# Optional/custom modules. There are tons available at
# https://github.com/boxen.
