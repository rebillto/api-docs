<p align="center">
  SURCO SEGUROS API DOCUMENTATION
</p>

<p align="center"><em>Visit the full API Docs from <a href="https://docs.surcoseguros.com.ar">the Surco Seguros API Docs Website</a> </em>.</p>

Getting Started with the project
------------------------------

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Fork this repository on GitHub.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/surcoseguros/api-docs.git`
3. `cd api-docs`
4. Initialize and start the project. You can either do this locally, or with Vagrant:

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at http://localhost:4567.

Now that the project is all set up on your machine, you'll probably want to learn more about [editing the markdown](https://github.com/lord/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/lord/slate/wiki/Deploying-slate).

If you'd prefer to use Docker, instructions are available [in the wiki](https://github.com/lord/slate/wiki/Docker).

### How to Build to statics
Execute: bundle exec middleman build --clean

### Note on JavaScript Runtime

For those who don't have JavaScript runtime or are experiencing JavaScript runtime issues with ExecJS, it is recommended to add the [rubyracer gem](https://github.com/cowboyd/therubyracer) to your gemfile and run `bundle` again.

Need Help? Found a bug?
--------------------

[Submit an issue](https://github.com/surcoseguros/api-docs/issues) to the GitHub Project if you need any help. And, of course, feel free to submit pull requests with bug fixes or changes.

<p><em>This documentation was created based on the <a href="https://lord.github.io/slate">Slate</a> open source project.</p>
