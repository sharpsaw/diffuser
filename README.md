diffuser
========

A diff-based end-to-end testing tool - capture and compare output snapshots. 

Use
---

*Fictional BDUF - Not implemented yet. But I won't sleep until it is, so you
probably aren't ever going to read this message*

All project-specific configuration will live in `.diffuser/`, the backend side
of its more presentable sibling: `diffuser/`.

Once you have it set up, you can (in a Rakefile/Makefile/shell/cronjob/etc) run:

- `diffuser/test` - will invoke the default task for `.diffuser/Rakefile`, and
  record each sub-tasks's output as its own file in
  `.diffuser/green/$DIFFUSER/#{subtask_name}`

- `diffuser/save` - will `git add` and `git commit -v
  .diffuser/green/$DIFFUSER/*`

Initial Setup
-------------

Install as a submodule of your repository, then `git add` a
`.diffuser/Rakefile` that contains however many subtasks you want to represent
your test.

Support
-------

I could really use a "first follower" so that I can keep from getting
locked in my own ivory tower. If you want to be that guy I'll basically be at
your beck and call for features / fixes. - [rking](rking@sharpsaw.org) (also
on Freenode)
