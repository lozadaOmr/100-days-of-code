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
