# Upcoming Changes

The following changes are slated for an upcoming release:

* Supply an entry point for a rubyist to run code before slides are
  generated. For example-- this code could define an HTML::Pipeline
  filter and then configure the filter to run over the slides. The
  proof of concept I've got in my mind is setting up notation along
  the lines of :emoji: but for font-awesome icons.

* Provide a notation to enable "Vertical Slides" when working in the
  DSL.

* ???

# Development

If you want to make changes to reveal-ck, you should first try the
following:

```
git submodule init
git submodule update
rake
```

The commands above get things online and verify basic functionality.

The submodule is necessary because reveal-ck relies on having a copy
of reveal.js (the original JavaScript based project) via a git
submodule.

## Testing

The testing strategy blends rspec and cucumber. There's not much going
on here (at a code level) so RSpec is straight forward. The
executable, reveal-ck, is verified as a command line tool with Aruba.

`rake spec` runs specs and `rake cucumber` runs features. `rake test`
runs both.

Running `rake` by default includes running RuboCop.

## Travis

This project is setup within Travis. Here is the
[project page](https://travis-ci.org/jedcn/reveal-ck).

Travis runs the default rake task and verifies specs, features, and
style conformity.

## Updating the embedded reveal.js

If you've got things checked out, and submodules inited, then you can
updated the embedded reveal.js as follows:

* cd into `files/reveal.js/`
* Run a `git fetch` and then merge/reset as is appropriate
* Run tests

[code-climate]: https://codeclimate.com/github/jedcn/reveal-ck.png
[travis]:       https://travis-ci.org/jedcn/reveal-ck.png
