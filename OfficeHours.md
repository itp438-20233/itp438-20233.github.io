---
title: Office Hours
parent: Syllabus
has_children: false
nav_order: 3
---

# Office Hours / Class Times

## Office Hours Expectations

There are quite a few office hours during the week, but there also are a lot of students in this class. To be respectful to both the professor/TAs and other students in the course, we want to lay out these expectations for what you should expect from the office hours:

* You should be ready explain what your issue is, what you’ve tried in the debugger so far, what you think might be the problem, and what advice you need to proceed
* You should ***NOT*** expect to just provide your code to a professor/TA and have them tell you what’s wrong with it – you have to make some effort to debug the problem yourself first. If it seems clear that you haven’t made an effort to debug the code yet, we will ask you to do that and help other students in the meantime
* We are happy to help you get on the right track, but we are ***NOT*** responsible for fixing all of your bugs – instead, we want you to learn how to understand and debug your code
* Keep in mind that we have a lot of students. After helping you for ~10 minutes, we will ask you to work on your assignment by yourself for a bit before getting further help. We will do this even if office hours are relatively light. (There are some exceptions to this, like if it’s a configuration or build problem that would prevent you from proceeding at all, but these issues are rare)

## Schedule

{% for schedule in site.schedules %}
{{ schedule }}
{% endfor %}
