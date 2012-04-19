diffuser
========

A diff-based end-to-end testing tool - capture and compare output snapshots. 

Use
---

*Fictional BDUF - Not implemented yet. But I won't sleep until it is, so you
probably aren't ever going to read this message*

- `.diffuser/` - contains all project-specific configuration in this
  "backend" directory. Most important is the `Rakefile`, whose `default` task
  is run to capture the output, and also the `green/` dir, where the output is
  actually captured.

The "frontend" to the process is commands like:

- `diffuser/test` - will invoke the default task for `.diffuser/Rakefile`, and
  record each sub-tasks's output as its own file in
  `.diffuser/green/$DIFFUSER/#{subtask_name}`

- `diffuser/save` - will `git add` and `git commit -v
  .diffuser/green/$DIFFUSER/*`

Initial Setup
-------------

From your project, do:

    git submodule add git://github.com/sharpsaw/diffuser.git
    diffuser/first-time

...this will:

1. Git-commit the addition of the submodule
2. Initialize/update the submodule directory (it starts out empty)
3. Add the test-case-containing [Rakefile](http://rake.rubyforge.org/)
4. Open an `$EDITOR` on the `.diffuser/Rakefile`
5. `git add .diffuser`
6. ...leaving the remainder to you, once you see if it's working or not.

Remember that each `rake` task will be parsed into its own file in
`.diffuser/green/$DIFFUSER/\*`. How you use this is up to your tastes -
sometimes all-in-one-big-file is nice, but other times you'll want to break it
up into more atomic bits.

Support
-------

I could really use a "first follower" so that I can keep from getting
locked in my own ivory tower. If you want to be that guy I'll basically be at
your beck and call for features / fixes. - [rking](rking@sharpsaw.org) (also
on Freenode)
