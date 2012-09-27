# Cleverbot

**Note: Nothing has been implemented yet. This document is a TODO list**

Cleverbot is a container for custom command line tools we use here at
Cleverific. The purpose of this tool is:

* Be the gateway/bootstrapper for working at and with Cleverific
* Capture institutional knowledge as code
* Make us awesome by automating routine tasks

Cleverbot is inspired by the `gh-setup` tool at Github. Mentioned here:
http://zachholman.com/talk/unsucking-your-teams-development-environment

Cleverbot is open source because sharing how we work helps us work better.

## Plugins

Cleverbot is built on top of Thor, which makes extension wonderfully simple.
While we keep as much of Cleverbot open source as possible, there are always a
few things that we need to keep internal. As such, you can configure Cleverbot
to point to a git repo of private extensions.

By default, cleverbot will check for updates to this repo's master branch once
per day and merge upstream any patches. You can add private plugin repos by
editing your `.cleverbotrc`.

Private plugin repos are cloned to `~/.cleverbot/plugins/`. You are also able
to configure which branch to checkout and frequency with which to check (daily
[default], hourly, weekly [by day of the week]). Cleverbot only checks for
updates when executed.

## Error Reporting

Should anything go wrong while `cleverbot` is doing its thing, an exception
will should be raised and cleverbot will automatically create a new issue in
Github for it. The issue is identified by exception type, file, and line
number in order to protect against duplicates.

When using Cleverbot for your own organization, you should fork this repo and
configure your `.cleverbotrc` with your fork and token credentials to receive
this error reporting.

Making sure there are never any issues with this tool is important so that
everyone can stay as productive as possible. Tools are a top priority.

## Installation

Install it yourself as:

    $ gem install cleverbot

## Usage

```
cleverbot bootstrap       # Bootstrap a new developer machine (Mac OS X only)
cleverbot rails new       # Our customized rails application generator
cleverbot setup <project> # Tell cleverbot to setup a project from your org
cleverbot gem new         # Wrapper around `bundle gem`
cleverbot gem push        # Like `gem push` but to your private gem server
cleverbot update          # Update cleverbot to the latest version
cleverbot help            # Help!
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
