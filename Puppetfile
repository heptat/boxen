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

github "boxen", "3.4.2"

# Support for default hiera data in modules

github "module-data", "0.0.3", :repo => "ripienaar/puppet-module-data"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "git",         "2.3.1"
github "nginx",      "1.4.3"
github "homebrew",    "1.9.2"
github "gcc",         "2.0.100"
github "openssl",    "1.0.0"
github "pkgconfig",  "1.0.0"
github "ruby",        "7.3.0"
github "stdlib",     "4.1.0", :repo => "puppetlabs/puppetlabs-stdlib"
github "repository",  "2.3.0"
github "redis",      "2.1.0"
# github "mysql",      "1.99.6"
github "mysql",      "1.2.0"
# github "mysql",      "1.2.3", :repo => "sidereel-dev/puppet-mysql"
github "vim",        "1.0.5"
github "tmux",       "1.0.2"
# mod "mysql", :git => "https://github.com/boxen/puppet-mysql"
# mod "mysql", :git => "https://github.com/sidereel-dev/puppet-mysql"
github "java",       "1.2.0"
github "iterm2",     "1.0.4"

# not sure about these - yes, they are required:
github "inifile",     "1.0.3", :repo => "puppetlabs/puppetlabs-inifile"
github "sudo",       "1.0.0"
github "xquartz",    "1.1.1"

# github "packer",    "1.2.1"

# Optional/custom modules. There are tons available at
# https://github.com/boxen.
