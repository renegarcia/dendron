---
id: 631hw9oh0k8jhc0wlm0joyz
title: Coding tips
desc: ''
updated: 1687107935898
created: 1685471254996
---


# Edit Git Remote URL 

```bash
git remote set-url origin <new-url>

```
[Source](https://chat.openai.com/share/5bbfc058-d6be-4ec8-b03f-be8df3619c37)



# Django tests not running

__Solution.__ Make sure you are writing your tests wrapped in classes that inherit from `TestCase`. Example:

```python
from django.test import TestCase


class FooTest(TestCase):
    def setUp(self):
        pass

    def tearDown(self):
        pass

    def test_this_will(self):
        print 'Win'
```

[Read more](https://stackoverflow.com/questions/2037364/django-test-runner-not-finding-tests)


# Python

[[code.python]]