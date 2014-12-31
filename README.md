Drupal Site Pre-commit Hooks
===========================
This git hook will fire on commit and check for:

- die()
- print\_r
- dpm (kpr and debug as well)
- console.log (JavaScript)
- Lorem ipsum
- PHP Linting
- Newline at end of file
- Incorrect line endings

This hook will only check features and custom directories (to reduce false positives
from contrib commits.)

Installing
----------
Run `curl -fsSL https://raw.githubusercontent.com/andrewmriley/drupal-site-precommit/master/install > install`
(or just download the install file however you want) and then in your repo's root
run `php install`.

*You may need to adjust the path to php or to the install file.*

That's it. Now when ever you run a commit the hook should fire and cancel the
commit if any of the above items are found in your commit. At this point you can
delete the install file or you can keep it around to update the pre-commit hook
as new versions come out.

Updating
--------
If you already have a copy of this pre-commit hook and you wish to update your
current version run `php install --update` and the old pre-commit hook will be
replaced with a freshly downloaded version.

Uninstalling
-----------
The install script will not automatically remove the pre-commit hook. If you do
wish to uninstall it, go to the root of your git repo and remove the .git/hooks/pre-commit
file.

*If you have made any changes to this file please make sure you have a backup.*

*Depending on your operating system or file browser settings directories that
start with a "." may be hidden by default.*

How to use
----------
Once you've run the installer on your repo the pre-commit hook will run every time
you try to run `git commit`. You'll see a note about it running and if there are
any errors, they will show up in your terminal and abort the commit. If there
are no errors than your commit will continue on as normal. This hook will not
modify your code in any way - it only warns you when the code you are trying to
commit has issues.

Overriding
----------
If you really need to commit code with the above mentioned items just run your
commit with a -n to skip the pre-commit hook.

Example: `git commit -n`

