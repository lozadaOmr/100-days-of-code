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

