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

A workaround I can think of is to make a  shared
directory between container and host. Not elegant but it should work.

**Link to work:** [Settings App](https://github.com/lozadaOmr/ansi-admin/pull/1)
