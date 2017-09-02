# 100 Days Of Code - Log


### Day 0: May 9, 2017

**Today's Progress**: Started with the Settings App.

**Thoughts:** Decided to take a dive in Django, I've only manage to go through the first few topics in the tutorial. I guess though both are MVC, it is a bit different from Laravel but it is "batteries included" compared to Flask.

**Link to work:** [Settings App](https://github.com/lozadaOmr/ansi-admin/tree/feature/settings-app)

---
### Day 1: May 10, 2017

**Thoughts:** Missed today. I needed to be accountable to my commitment.

---
### Day 2: May 11, 2017

**Today's Progress**: Completing the CRUD part of the Settings App.
Learned more about creating models.

**Thoughts**: Encountered trouble such as migrate not detecting changes in my models.
I also realized I should have created a proper gitignore from the start.

Tricky part was defining the 'path'.
Had trouble trying to make `FilePathField` to work,
which is more like I got confused with the usage of FilePathField over filesystem
storage class.

Thinking of using CharField in the meantime to represent the path.
Much be nicer if this was properly implemented.

Maybe should not have squash the commits. Also not delete branches.

Might need to figure a way to browse filesystems. Given the limitation
that I'm running the app using Docker which might be problem, since I can't access
the actual host's filesystem.

~~A workaround I can think of is to make a  shared
directory between container and host. Not elegant but it should work.~~

*TIL* Directories added during docker build can't be changed.

**TODO**:

- [x] Find a way to trigger Ansible from Django Admin


**Link to work:** [Settings App](https://github.com/lozadaOmr/ansi-admin/pull/1)

---
### Day 3: May 12, 2017

**Today's Progress**: Made some proof of concept so that Ansible Playbooks
from Djago Admin

**Thoughts**: Options that I can further explore Python `os.system` eventually
I think I would need implement celery.

**Links to work**:

* [ansi-admin registry](https://hub.docker.com/r/lozadaomr/ansi-admin/tags/)
* [Ansible Django Integration](https://github.com/lozadaOmr/ansi-admin/tree/feature/django-ansible-integration)

---
### Day 4: May 13, 2017

**Today's Progress**: Continued working with Django, this time taking a deep dive
on how to work with Templates, Forms. Also renamed Settings App into Ansible.


**Thoughts**: Had trouble on how to add custom template in Django Admin.
Initial implementation points to using `os.system`, after some reading I might
go with using `subprocess`
This is one of those moments where you thought implementation would be easy
**BUT NOPE**, stdout is displayed in the logs but getting some error.
Thinking of spending the rest of day going through the Django Tutorial.

**Link to work**:

* [Ansible Django Integration](https://github.com/lozadaOmr/ansi-admin/tree/feature/django-ansible-integration)
* [Renamed Settings App](https://github.com/lozadaOmr/ansi-admin/pull/3)

**TODO**:

- [ ] Improve subprocess call on views.py
- [ ] Might need celery to handle queue
- [x] Check if this will work - instead of defining a path to where playbooks and configs
are located; give a defined path instead probably in directory added before container
builds

___
### Day 5: May 14, 2017

**Today's Progress**: Learned about fixtures and added it for Ansible app.

**Thoughts**: Time mostly spent on following Django Polls app tutorial.

**Link to work**:

* [Initial App Fixture](https://github.com/lozadaOmr/ansi-admin/pull/4)

___
### Day 6: May 15, 2017

**Today's Progress**: Updated the container's Ansible to use latest (2.3.0),
Add a directory where playbooks will be added. Worked on creating the apps
Ansible registry.

**Thoughts**: Started playing with Django Models, trying to figure out how
relationship works.

**Link to work**:

* [Playbooks Directory](https://github.com/lozadaOmr/ansi-admin/pull/5)
* [Ansible Registry](https://github.com/lozadaOmr/ansi-admin/pull/7)

___
### Day 7: May 16, 2017

**Today's Progress**: Continued working with Django Models

**Thoughts**: Tried removing some parts since I can't fully express why it was
needed in the first place. After awhile, I managed to rationalize why I them.
Teardown was an important part of reflection on which is which.

**Link to work**:

* [Ansible App](https://github.com/lozadaOmr/ansi-admin/tree/feature/ansible-app)

___
### Day 8: May 17, 2017

**Today's Progress**: Continue work on Django Models

**Thoughts**: Started to get comfortable with Django Models after almost 3 days

**Link to work**:

* [Ansible App](https://github.com/lozadaOmr/ansi-admin/tree/feature/ansible-app)

___
### Day 9: May 18, 2017

**Today's Progress**: Create a Repository model to store Git Repo of Playbooks
template

**Thoughts**: For now I should handle public GitHub repos

**Link to work**:

 * [Ansible App](https://github.com/lozadaOmr/ansi-admin/tree/feature/ansible-app)

 ___
### Day 10: May 19, 2017

 **Today's Progress**: Started working on Repository app

 **Thoughts**: Use repository app to trigger clone of Playbook from GitHub
 Got stuck troubleshooting a bug

Thinking of continuing working on Repository app in a different branch

 **Link to work**:

 * [Ansible App](https://github.com/lozadaOmr/ansi-admin/tree/feature/ansible-app)

 ___
### Day 11: May 20, 2017

 **Today's Progress**: Testing out GitPython for cloning git repositories

 **Thoughts**: Spent most of the time going through documentation.
 Trying to 'git clone' from Django.

 Realized there are other ways to clone a git repository.

 **Link to work**:

* [Repository App](https://github.com/lozadaOmr/ansible-admin/tree/feature/repository-app)

___
### Day 12: May 21, 2017

**Today's Progress**: Continue  working on Repository App

**Thoughts**: Somehow playbook mounted volume is not elegant

**Link to work**:

* [Repository App](https://github.com/lozadaOmr/ansible-admin/pull/11)

___
### Day 13: May 22, 2017

**Today's Progress**: Bug Fix on Repository App

**Thoughts**: Just need to figure out how to override Django Admin's bulk delete
method

**Link to work**:

* [Repository App](https://github.com/lozadaOmr/ansible-admin/tree/cleanup/repository-app)

___
### Day 14: May 23, 2017

**Today's Progress**: Finally Fixed bug on Repository app's bulk delete

**Thoughts**: Learned how to use QuerySet as manager to override Django
admin's bulk delete.

Recent error encountered was caused by QuerySet not being first.
Maybe I should file issues if I encounter bugs on my projects for documentation.

**Link to work**:

* [Repository App](https://github.com/lozadaOmr/ansible-admin/pull/12)

___
### Day 15: May 24, 2017

**Today's Progress**: Tried to implement Abstract Base class

**Thoughts**: Suprised it worked.

**Link to work**:

* [Abstract Base Class](https://github.com/lozadaOmr/ansible-admin/pull/14)

___
### Day 16: May 25, 2017

**Today's Progress**: Some fixes on Ansible app. Started working with forms and
custom templates

**Thoughts**:

**Link to work**:

* [Ansible App Fix](https://github.com/lozadaOmr/ansible-admin/pull/15)

___
### Day 17: May 26, 2017

**Today's Progress**: Initial implementation of GitLab repository

**Thoughts**: Tried first implementing using ssh, which result in error.
Implementation for now would use https instead

**Link to work**:

* [Gitlab class](https://github.com/lozadaOmr/ansible-admin/pull/16)

___
### Day 18: May 27, 2017

**Today's Progress**: Started working on es-curator module for Ansible

**Thoughts**: Need to take a break from Django. Decided to take a break and start
another Python project that I might be using soon. Spent most of the time
reading through Ansible's developer documentation

**Link to work**:

* [es-curator module](https://github.com/lozadaOmr/es-curator/commit/896428cd0888f4ad6a5ed2973086eb468681f549)

---
### Day 19: May 28, 2017

**Today's Progress**: Conitnue working on es-curator module for Ansible

**Thoughts**: Initially thought of adding `dry_run` args; but realized it should
be in line with Ansible's `--check` flag (Thinking of implementing later)

**Link to work**:

* [ES-Curator Ansible Module](https://github.com/lozadaOmr/es-curator)

___
### Day 20: May 29, 2017

**Today's Progress**: Worked through most functionality of es-curator module

**Thoughts**: `import subprocess` is different from `from subprocess import ...`
Just need to make Popen() work and the module would be usable-ish

**Link to work**:

* [ES-Curator Ansible Module](https://github.com/lozadaOmr/es-curator/tree/use-subprocess-popen)

___
### Day 21: May 30, 2017

**Today's Progress**:
- Managed to complete es-curator module
- Refactor validation
- Add support for `check_mode (dry-run)`
- Add RETURN block for Ansible docs

**Thoughts**: Finally managed to get it working, thanks to this [guide](http://sharats.me/the-ever-useful-and-neat-subprocess-module.html)

**Link to work**:

* [ES-Curator Ansible Module](https://github.com/lozadaOmr/es-curator/)
* [RETURN block](https://github.com/lozadaOmr/es-curator/pull/4)
* [Refactor Validation](https://github.com/lozadaOmr/es-curator/pull/3)
* [Support check_mode](https://github.com/lozadaOmr/es-curator/pull/2)

___
### Day 22: May 31, 2017

**Today's Progress**: Fix an [issue](https://github.com/lozadaOmr/es-curator/issues/5) where an error was not raised if
remote host doesn't have curator's config yaml on the default location.

**Thoughts**: I initially intended to use Ansible's `setup_facts` to get the remote Host's
HOME directory. Today I learned, same can be achieved using Python

```
import getpass

homedir = getpass.getuser()
```

**Link to work**:

* [ES Curator Ansible Module Fix](https://github.com/lozadaOmr/es-curator/pull/6)

___
### Day 23: June 01, 2017

**Today's Progress**:

* Work on validating if curator is installed on remote host.
* Use AnsibleModule's `run_command()`

**Thoughts**: Appreciate Python, and it's capability to interact with OS.
Also, instead of using Python's Popen() -- just used Ansible's `run_command()` which
is a wrapper for Python's Popen()

**Link to work**:

* [Ansible run_commnad](https://github.com/lozadaOmr/es-curator/pull/8)
* [Check if curator is installed](https://github.com/lozadaOmr/es-curator/pull/7)

___
### Day 24: June 02, 2017

**Today's Progress**: Rewrite ES-curator's `main()` func to run validations first.

**Thoughts**: Spent today trying to rewrite the `validate()` and
`get_default_config()`command into one. But couldn't figure out how.

**Link to work**:

* [ES-curator Ansible Module](https://github.com/lozadaOmr/es-curator/pull/9)

___
### Day 25: June 03, 2017

**Today's Progress**: Move ansi-admin's Repository app to Ansible app

**Thoughts**: Getting confused how to do multiple apps, decided that in order to move forward
just combine both apps.

**Link to work**:

* [ansi-admin](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 26: June 04, 2017

**Today's Progress**: Back to creating HTML forms and pages

**Thoughts**: Reading through lots of documentation between Django's template/forms and Jinja2 template.

**Link to work**:

* [ansi-admin](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 27: June 05, 2017

**Today's Progress**: Manage to make the form use Bootstrap CSS

**Thoughts**: Had to remember though Flask also used Jinja templating there would be some difference compared to Django.
Django needs `{% load staticfiles %}` while for when I was using Flask static file URL was
hardcoded.

Maybe checkout using Form Wizard to handle multi-step forms.

**Link to work**:

* [ansi-admin](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 28: June 06, 2017

**Today's Progress**: Save data from Django custom form

**Thoughts**: Intially attempted to create forms from ModelForm but for now could not make it to work

**Link to work**:

* [ansi-admin](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 29: June 07, 2017

**Today's Progress**: Fix error when deleting non-existing directory

**Thoughts**: Busy day, exactly got one hour, decided to fix bug instead.

**Link to work**:

* [Fix OS Error - Ansi Admin](https://github.com/lozadaOmr/ansible-admin/pull/20)

___
### Day 30: June 08, 2017

**Today's Progress**: Started learning to use Django's formtools

**Thoughts**: Finally making steady progress a few more and I might be comfortable using
forms and templates with Django, although it was a lot of documentation to read

**Link to work**:

* [Django's formtools](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 31: June 09, 2017

**Today's Progress**: Finally figured out how to pass previous input to current form

**Thoughts**:

**Link to work**:

* [Working with Django's formtools](https://github.com/lozadaOmr/ansible-admin/commit/343e310d9938a7b192cc72de6969bd74938f334d)

___
### Day 32: June 10, 2017

**Today's Progress**: Managed to save finish the basic flow of saving two models using Django Form Wizard

**Thoughts**:

* Learned how it is much simple to use ModelForm when working with Form Wizard, it is a much DRY approach than
coding again the fields of the model in forms.py

**Link to work**:

* [Django ModelForm](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 33: June 11, 2017

**Today's Progress**: Save form data on each Form step

**Thoughts**: Instead of using `SessionWizardView.done()` to save forms tried hooking it up on
`SessionWizardView.get_form_step_data()` (Not yet even sure if this is what I should be doing). 
I figured I just need a way to traverse the repository directory to provide the files when
user is on PlaybookWizard step 2.

**Link to work**:

* [Django ModelForm](https://github.com/lozadaOmr/ansible-admin/tree/feature/add-custom-views)

___
### Day 34: June 12, 2017

**Today's Progress**: Add validation check if inventory file exist when creating playbook

**Thoughts**: First method attempt to implement was trying to hook it up on `forms.py`,
Later found that much better to be included in `models.py`.

Not sure if this should be moved into its own custom `Validators`
But for now you can't save the playbook if the inventory file you supplied does not exists.

Additional Validation should follow

**Link to work**:

* [Check if Ansible inventory exists](https://github.com/lozadaOmr/ansible-admin/pull/26)

___
### Day 35: June 13, 2017

**Today's Progress**: Add validation check if repository directory exist when creating repository

**Thoughts**: Was hoping to make the `ValidationError` display on the page, but got some weird results when
I tried to implement the same pattern with how validated the inventory file of the playbook.

**Link to work**:

* [Check if Ansible repository exists](https://github.com/lozadaOmr/ansible-admin/pull/27)

___
### Day 36: June 14, 2017

**Today's Progress**: Experiement on different Validation and Exception methods in Django

**Thoughts**: Today I learned you can also have `clean()` in forms.py

**Link to work**:

* [ValidationErrors in ansible-admin](https://github.com/lozadaOmr/ansible-admin/tree/rewrite-check-repository-exists)

___
### Day 37: June 15, 2017

**Today's Progress**: Tried implementing valadition on forms.py `clean_*()`
 
**Thoughts**: Still not getting the desired output, might need to check Validators next

**Link to work**:

* [ValidationErrors in ansible-admin](https://github.com/lozadaOmr/ansible-admin/tree/rewrite-check-repository-exists)

___
### Day 38: June 16, 2017

**Today's Progress**: Simpler check_repository_exists() method
 
**Thoughts**: Still don't know why `os.path.exists()` returns `True` for some reason.
Learned that specific validators should be implemented in the form's `clean_<FIELD NAME>()`,
because running it on the ModelForm's `clean()` method will result in being run for each field you have in the model.

Interesting thing happened is when you realize not everything should be inside an [IF statement block](https://github.com/lozadaOmr/ansible-admin/commit/934d1ad76dc3f2ffba9abf0cfe11450ab592cb86)

**Link to work**:

* [ValidationErrors in ansible-admin](https://github.com/lozadaOmr/ansible-admin/tree/rewrite-check-repository-exists)

___
### Day 39: June 17, 2017

**Today's Progress**: Experimenting on how to handle this kind of custom validation
 
**Thoughts**: Checked that when running `self.instance.check_repository_exists()` in the `forms.py`
`self.reposiory` was blank making the method return only the `setting.PLAYBOOK_DIR` which result in a
`True`-thy value (because settings.PLAYBOOK_DIR actually exist).

Might actually resolve to moving validation to a separate `validators.py`

**Link to work**:

* [ValidationErrors in ansible-admin](https://github.com/lozadaOmr/ansible-admin/tree/rewrite-check-repository-exists)

___
### Day 40: June 18, 2017

**Today's Progress**: Tried using `NamedUrlWizardView`
 
**Thoughts**: Things got frustrating managed to fix the validationerror return always `True`
by using `self.cleaned_data['repository']` instead of `self.repository`.

The problem now is after submitting the step2 form, it redirects to step1. Raising 'repository exist' validation error.
Even though both form data where saved. What is strange is i'm reaching the `done()` method.

It could be because I save the form data for every step.
Or something with the `models.py`'s `save()` getting messed up.

**Link to work**:

* [ValidationErrors in ansible-admin](https://github.com/lozadaOmr/ansible-admin/tree/rewrite-check-repository-exists)

___
### Day 41: June 19, 2017

**Today's Progress**: Thinking problem might be to having multiple model, rewrite all into one to test
 
**Thoughts**: Not much time to code, got caught up with work.

**Link to work**:

* [Model Rewrite](https://github.com/lozadaOmr/ansible-admin/tree/unified-model-rewrite)

___
### Day 42: June 20, 2017

**Today's Progress**: Revisit previous solution continue moving methods to forms.py
 
**Thoughts**:

**Link to work**:

* [Model Rewrite](https://github.com/lozadaOmr/ansible-admin/commit/a274cc89047e1b7cbd28b278bfac9e79cf88f271)

___
### Day 43: June 21, 2017

**Today's Progress**: Done moving methods from `models.py` to `forms.py`
 
**Thoughts**: Trying to figure out where to hook my clone_repository() method

**Link to work**:

* [Model Rewrite](https://github.com/lozadaOmr/ansible-admin/commits/unified-model-rewrite)

___
### Day 44: June 22, 2017

**Today's Progress**: After asking around got an idea on how to make work, by moving it all to
`views.py` in `done()` method.
 
**Thoughts**:

**Link to work**:

* [Model Rewrite](https://github.com/lozadaOmr/ansible-admin/pull/29)

___
### Day 45: June 23, 2017

**Today's Progress**: Finally completed migration by moving it to `views.py`
 
**Thoughts**: Decided to code early in the morning. Makes a lot of difference
rather than rushing to find a solution before the day ends.

**Link to work**:

* [Migrate validations](https://github.com/lozadaOmr/ansible-admin/pull/32)

___
### Day 46: June 24, 2017

**Today's Progress**: Move methods to `utils` file
 
**Thoughts**: Not entirely Django related reading, but more of general Python.
[An opinionated guide to Python](http://python-guide-pt-br.readthedocs.io/en/latest/writing/structure/)

**Link to work**:

* [Utils](https://github.com/lozadaOmr/ansible-admin/pull/33)

___
### Day 47: June 25, 2017

**Today's Progress**: Started working on custom auth pages
 
**Thoughts**: 

**Link to work**:

* [Custom Auth Pages](https://github.com/lozadaOmr/ansible-admin/tree/feature/custom-login)


___
### Day 48: June 26, 2017

**Today's Progress**: Learned to make use of Django AUTH
 
**Thoughts**: Yup, good thing I don't have to roll-my-own authentication for now.

**Link to work**:

* [Custom Auth Pages](https://github.com/lozadaOmr/ansible-admin/tree/feature/custom-login)

___
### Day 49: June 27, 2017

**Today's Progress**: Redirect authenticated user
 
**Thoughts**: 

**Link to work**:

* [Custom Auth Pages](https://github.com/lozadaOmr/ansible-admin/tree/feature/custom-login)

___
### Day 50: June 28, 2017

**Today's Progress**: Started using Django's Generic Views
 
**Thoughts**: Started on a new feature. A bit tired, will continue work tomorrow.

**Link to work**:

* [Playbook directory traversal](https://github.com/lozadaOmr/ansible-admin/tree/feature/traverse-playbook-directory)

___
### Day 51: June 29, 2017

**Today's Progress**: Worked on `list_playbook_files()` that would display yaml files in current playbook dir
 
**Thoughts**: 

* fixed issue on 'create' uri being parsed as `pk`
* added link to playbook detailed view
* also decided to save directory as full-path

**Link to work**:

* [Playbook directory traversal](https://github.com/lozadaOmr/ansible-admin/tree/feature/traverse-playbook-directory)

___
### Day 52: June 30, 2017

**Today's Progress**: Learned working with Jinja templates in Django
 
**Thoughts**: Was not feeling enthusiastic today.

**Link to work**:

* [Playbook directory traversal](https://github.com/lozadaOmr/ansible-admin/tree/feature/traverse-playbook-directory)

___
### Day 53: July 01, 2017

**Today's Progress**: Display Playbook File contents in Django. Test on STDOUT
 
**Thoughts**: DJANGO REGEX URLS is HARD. Me SAD.

**Link to work**:

* [Display Playbook File Contents](https://github.com/lozadaOmr/ansible-admin/commits/feature/display-playbook-content)

___
### Day 54: July 02, 2017

**Today's Progress**: Trying out different ways to display YAML file content to view
 
**Thoughts**: First attempt result in content being display but line breaks where not preserved

**Link to work**:

* [Display Playbook File Contents](https://github.com/lozadaOmr/ansible-admin/commits/feature/display-playbook-content)

___
### Day 55: July 03, 2017

**Today's Progress**: Included `content_type` in `HttpResponse()`
 
**Thoughts**: Was expecting to that in order make it work, I'd have to install some other Django app.
Or maybe use some advance template/view methods. Apparently it was just as simple as including the `content_type`

**Reference**: [Serve a text file](https://stackoverflow.com/questions/14503062/how-do-i-serve-a-text-file-from-django)

**Link to work**:

* [Display Playbook File Contents](https://github.com/lozadaOmr/ansible-admin/commits/feature/display-playbook-content)

___
### Day 56: July 04, 2017

**Today's Progress**: Started working with how to run playbook files
 
**Thoughts**:

**Link to work**:

* [Run Playbook Files](https://github.com/lozadaOmr/ansible-admin/tree/feature/run-playbook-files)

___
### Day 57: July 05, 2017
 
**Thoughts**: Missed chance to code. Due to lot of tasks at work.

___
### Day 58: July 06, 2017

**Today's Progress**: Working on Django templates and views to run selected playbook file
 
**Thoughts**:

**Link to work**:

* [Run Playbook Files](https://github.com/lozadaOmr/ansible-admin/tree/feature/run-playbook-files)

___
### Day 59: July 07, 2017

**Today's Progress**: Prepared ansi-admin docker image with Ansible
 
**Thoughts**: Spent time solving trivial issue. I forgot to include Ansible in the container build

**Link to work**:

* [Run Playbook Files](https://github.com/lozadaOmr/ansible-admin/tree/feature/run-playbook-files)

___
### Day 60: July 08, 2017

**Today's Progress**: Completed simple POC for running Ansible using subprocess
 
**Thoughts**:

**Link to work**:

* [Complete Playbook Files](https://github.com/lozadaOmr/ansible-admin/pull/37)

___
### Day 61: July 09, 2017

**Today's Progress**: Wanted to test a new feature, where progress of playbook run is streamed to view
 
**Thoughts**:

**Link to work**:

* [Display STDOUT to View](https://github.com/lozadaOmr/ansible-admin/commit/4eaa969fc0f20b01a05c0d20a40aff771ff261e7)

___
### Day 62: July 10, 2017

**Thoughts**: Was too tired and haven't got a sleep. Went to take a nap after work. 
 
___
### Day 63: July 11, 2017

**Thoughts**: Was not able to code today either. Too tired :( 

___
### Day 64: July 12, 2017

**Today's Progress**: Testing how to use StreamingHttpResponse with STDOUT to view
 
**Thoughts**:

**Link to work**:

* [Display STDOUT to View](https://github.com/lozadaOmr/ansible-admin/commit/7c2dc1d5a29651fa7c1f544e88a2ed25de52b595)

___
### Day 65: July 13, 2017

**Today's Progress**: Started learning about Django Tests
 
**Thoughts**: Decided to work on something different in the meantime, I don't think streaming STDOUT is handled soley using python.

**Link to work**:

* [Django Unit Test](https://github.com/lozadaOmr/ansible-admin/commit/1ba0c1f87bbb79f13a8ee0ce8525692d35266037)

___
### Day 66: July 14, 2017

**Today's Progress**: Learned more about testing structure in Django
 
**Thoughts**: Originally tried using sqlite3 for testing. Decided to just use root database password for dev testing instead.

**Link to work**:

* [Django Unit Test - Models](https://github.com/lozadaOmr/ansible-admin/commit/e39d37ddb26f97ec8d93acb7e8d1ad9e1699c11b)

___
### Day 67: July 15, 2017

**Today's Progress**: Created tests for Views in Django
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Views](https://github.com/lozadaOmr/ansible-admin/commit/39b0cfe15c2e0409e134cabd8fc48c42154bb359)

___
### Day 68: July 16, 2017

**Today's Progress**: Created tests for Forms in Django
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Forms](https://github.com/lozadaOmr/ansible-admin/commit/8427eb485d64a97e09a0f77e84beeade605fcd9c)

___
### Day 69: July 17, 2017

**Today's Progress**: Test form validation errors in Django
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Forms](https://github.com/lozadaOmr/ansible-admin/commit/fe2271846ed7a73f1e4e7a2f3d7fef8a1f92a166)

___
### Day 70: July 18, 2017

**Today's Progress**: Test custom utils
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Utils](https://github.com/lozadaOmr/ansible-admin/commit/8d74aa7fa22ed878199dfb8ad887d89e3b46dda9)

___
### Day 71: July 19, 2017

**Today's Progress**: Test custom util validators
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Validators](https://github.com/lozadaOmr/ansible-admin/commit/b705695b39c8845a33d360158a9b93fd8be06e00)
* [Django Unit Test - Use setUp()](https://github.com/lozadaOmr/ansible-admin/commit/68f53afbb8e020a2fb2f852eb720ebe2c492e867)
* [Django Unit Test - Use self.playbook](https://github.com/lozadaOmr/ansible-admin/commit/8f5286b37cbc8118e0f3ee5ca810b0a808d4aa6b)

___
### Day 72: July 20, 2017

**Today's Progress**: Went back to making test for Views
 
**Thoughts**: 

**Link to work**:

* [Django Unit Test - Views](https://github.com/lozadaOmr/ansible-admin/commit/c2aa6a48bbbf33abbb82a1dbc7dc10cd83594b1a)

___
### Day 73: July 21, 2017

**Today's Progress**: Started working with integration tests

**Thoughts**: not sure if this will work though.

**Link to work**:

* [Django Unit Test - Integration](https://github.com/lozadaOmr/ansible-admin/commit/453b25c302969c2f550514a39b5abfd7fdb37bbe)

___
### Day 74: July 22, 2017

**Today's Progress**: Fixed some error when running unit tests

**Thoughts**: Can figure out how to perform integration test, decided to fix some unit test error instead.

Need to think of a better to setup tests, which include probably mocking OS level operations (create directory etc.)

**Link to work**:

* [Django Unit Test - Fixes](https://github.com/lozadaOmr/ansible-admin/commit/016d53467b39b7c3ae4f7e9969d65a7b58cb5f55)

___
### Day 75: July 23, 2017

**Today's Progress**: Attempt to use Python mock library

**Thoughts**: Tried learning to use python mock library, but can't make it to work

**Link to work**:

* [Django Unit Test - Remove invalid tests](https://github.com/lozadaOmr/ansible-admin/commit/ea68fa1f1150d33e3c8d6bccf11621b41206bdc2)

___
### Day 76: August 13, 2017

**Today's Progress**: Worked on making local Playbook files editable

**Thoughts**: After taking 20 days to rest *(Some unfortunate stuff happened, resulting me being burnt out)*. Decided it's about time to go back and start coding again.

I think I may have to adjust some of the rules that I will be following for round 2.

**Link to work**:

* [Django - Editable Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/168d385325b77937dd40e77ae166f29610c9a137)

___
### Day 77: August 14, 2017

**Today's Progress**: Continue working on Editable Playbook files, improve code using utils.

**Thoughts**: 

**Link to work**:

* [Django - Editable Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/99d3bb14a8caa6b303da1178411a74ed372bb735)

___
### Day 78: August 15, 2017

**Today's Progress**: Spent time trying to figure out to properly display TextArea

**Thoughts**: For now it is as hardcoded as `attrs`

**Link to work**:

* [Django - Editable Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/269bd116c1900eb3ceef9a9abec84354734932ea)

___
### Day 79: August 16, 2017

**Today's Progress**: Working saving changes to local file in the server

**Thoughts**: 

**Link to work**:

* [Django - Editable Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/580c06185fb602a5d5e5a4736dadea9a5cb8b993)

___
### Day 80: August 17, 2017

**Today's Progress**: Missed day 80

___
### Day 81: August 18, 2017

**Today's Progress**: Manage to write changes to local file in the server

**Thoughts**: 

**Link to work**:

* [Django - Editable Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/e8d2521a4487fa57dd2b1cb5e8e217eaf068ee1c)

___
### Day 82: August 19, 2017

**Today's Progress**: Move everything to a util function, keeps the views neat.

**Thoughts**: 

**Link to work**:

* [Django - Editable Playbook files Utils](https://github.com/lozadaOmr/ansible-admin/tree/bb9d7fe6bbb3cb0e49755541aef31aa796bdcd7b)

___
### Day 83: August 20, 2017

**Today's Progress**: Adding new feature to create playbookfiles and save locally

**Thoughts**: Working  again on Django templates, views, forms, urls. I think this would be a good exercise to familiarize with the flow.

**Link to work**:

* [Django - Add Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/223cb7dcf1e613311c681cbccbd0131b28f0d081)

___
### Day 84: August 21, 2017

**Today's Progress**: Continue working feature to create playbookfiles and save locally

**Thoughts**: Struggled working with URL conf, not sure why I can't use Jinja tag like `{% url 'ansible:playbook-file-create' pk %}` even when I know the regex is like so `r'^(?P<pk>[-\w]+)/files/new/$'`. For a moment I thought it was how I arranged the URls but still got the error, temporary solution was to use hardcode URLs in the form

**Link to work**:

* [Django - Add Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/3c7bdea1c71503c78bae027ad2e0199d24349542)

___
### Day 85: August 22, 2017

**Today's Progress**: Saved form POST to local file

**Thoughts**: Thinking of rewriting this part, seemed there are better ways of doing it.

**Link to work**:

* [Django - Add Playbook files](https://github.com/lozadaOmr/ansible-admin/commit/d858a6d2eddff4f37f93e2218409ce3245d7b130)

___
### Day 86: August 23, 2017

**Today's Progress**: Move some code to utils

**Thoughts**: I think I should revist writing tests for some of the new features I created recently

**Link to work**:

* [Django - Add Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/414c4fd6ef28f1135d0c49774b6910f8d25363b4)

___
### Day 87: August 24, 2017

**Today's Progress**: Added some unit tests for Playbook utils

**Thoughts**:

**Link to work**:

* [Django - Add Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/cd324ec0c94dff349e95c85c95d6726acfb4291a)

___
### Day 88: August 25, 2017

**Today's Progress**: Worked on validating the filename of the newly created Playbook file

**Thoughts**:

**Link to work**:

* [Django - Validating Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/72fac582266f34212f533f15a3f1ccaaa6e00392)

___
### Day 89: August 26, 2017

**Today's Progress**: Away from coding for today. Long weekend it is.

___
### Day 90: August 27, 2017

**Today's Progress**: Completed Adding form validation  

**Thoughts**:

**Link to work**:

* [Django - Validating Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/42ed07889652c3c4e56e69398f9ef8541c3a148b)

___
### Day 91: August 28, 2017

**Today's Progress**: Away from coding for today.

___
### Day 92: August 29, 2017

**Today's Progress**: Fixed bug where error message is displayed for each field

**Thoughts**: Not yet sure why `{{ form.as_p }}` rendered it properly. Might need to get back at it and figure out why

**Link to work**:

* [Django - Validating Playbook files](https://github.com/lozadaOmr/ansible-admin/tree/be7cbb57f1cf40f5a4a39269e144ed9538e461fa)

___
### Day 93: August 30, 2017

**Today's Progress**: Made ansible views.py into PEP8 code style

**Thoughts**: There seems to be a Python PEP8 and also Django's coding style PEP8

**Link to work**:

* [Django - PEP8](https://github.com/lozadaOmr/ansible-admin/tree/52ab9de98f337de489bd8e4cad696c9301a35246)

___
### Day 94: August 31, 2017

**Today's Progress**: Continued applying PEP8 code style

**Thoughts**:

**Link to work**:

* [Django - PEP8](https://github.com/lozadaOmr/ansible-admin/tree/221488aff3e2628d304cc3d19dad2c0e5d5a9106)

___
### Day 95: September 01, 2017

**Today's Progress**: Continued applying PEP8 code style

**Thoughts**: Discovered that one of the tests failed. I might have to check why it failed next.

**Link to work**:

* [Django - PEP8](https://github.com/lozadaOmr/ansible-admin/tree/abedc8b4ad17bc745df5cc1e04b7cf09250a051b)

___
### Day 96: September 02, 2017

**Today's Progress**: Bug when running all unit tests

**Thoughts**: Manage to narrow it down to both `test_models.py` and `test_views.py` since both use `setUpTestData()` I'm thinking it could be because after the set up is ran on when of the TestCase it doesn't tear down.

Options to validate this is idea I think:
- a function that will act as global setup
- probably look into using fixtures instead

**Link to work**:

* [Django - Fix Unit Test](https://github.com/lozadaOmr/ansible-admin/tree/5e0f881a366f49421cd6f05ac0da02494d957872)
