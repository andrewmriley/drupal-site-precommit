Drupal Site Pre-commit Hooks
===========================
This git hook will fire on commit and check for:

- die()
- print_r
- dpm
- console.log (JavaScript)
- Lorem ipsum

This hook will only check features and custom directories (to reduce false positives
from contrib commits.)

Install
-------
Run `curl -fsSL http://gitscripts.s3.amazonaws.com/install` (or just download
the install file however you want) and then in your repo's root run (you'll
probably need to adjust the path to install) `php install`.

That's it. Now when ever you run a commit the hook should fire and cancel the
commit if any of the above items are found in your commit.

Overriding
----------
If you really need to commit code with the above mentioned items just run your
commit with a -n to skip the pre-commit hook.

Example: `git commit -n`

