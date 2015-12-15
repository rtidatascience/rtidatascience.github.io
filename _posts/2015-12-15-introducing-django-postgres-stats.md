---
layout: post
title: Introducing django-postgres-stats
author: Clinton Dreisbach
---

While working on a dashboard project that used Django, I found myself
reaching for functions in PostgreSQL to generate time series data and
calculate percentiles. In Django 1.8,
[`Func()` expressions were added][1] to let users access
database-specific functions more easily. Django subclasses `Func` to
give you [common database functions][2], so I did the same to expose
some [PostgreSQL date/time functions][3] and a percentile function from
the [PostgreSQL aggregate functions][4].

Since we're likely to need these same functions in future projects and
I didn't have much practice building Python packages, I wrapped the
functions up and open-sourced them. You can [read the docs][] and
[check out the source code][].

One thing I enjoyed about packaging up the code is using [pbr][] to
build the package on the recommendation of
[The Hacker's Guide to Python][hgp]. I found it hard to find what I
needed in the documentation, but it was nice to use besides
that. Using git tags and `requirements.txt` -- two things I was
already using -- to version the package and set the requirements was
great.

[1]: https://docs.djangoproject.com/en/1.8/ref/models/expressions/#func-expressions
[2]: https://docs.djangoproject.com/en/1.8/ref/models/database-functions/
[3]: http://www.postgresql.org/docs/current/static/functions-datetime.html
[4]: http://www.postgresql.org/docs/9.4/static/functions-aggregate.html
[read the docs]: https://django-postgres-stats.readthedocs.org/en/latest/
[check out the source code]: https://github.com/rtidatascience/django-postgres-stats
[pbr]: http://docs.openstack.org/developer/pbr/
[hgp]: https://julien.danjou.info/books/the-hacker-guide-to-python/
