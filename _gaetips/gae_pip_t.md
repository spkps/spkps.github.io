---
title: 'pip --target: no such option'
---
Third-party libraries which are not provided by GAE may be deployed directly into the cloud with project's. To simplify the packages management in that case `pip` has `-t, --target` parameter. This practice is well described in <a href="https://cloud.google.com/appengine/docs/python/tools/libraries27#vendoring" target="_blank">GAE documentation</a>.

However, sometimes it may not work from the scratch. At least, under my Ubuntu I saw `no such option` error.

{% highlight bash %}
>>> pip install flask -t libs/
Usage: /usr/bin/pip install [OPTIONS] PACKAGE_NAMES...

/usr/bin/pip install: error: no such option: -t
{% endhighlight %}

After searching the Web a little, the cause has been found -- `pip` was installed in a "wrong" way. I've installed it as a lot of another tools on Ubuntu with `apt` utility. But the right way is an installation as it described in <a href="https://pip.pypa.io/en/stable/installing/" target="_blank">the official `pip` documentation</a> with `get-pip.py` script. Also it works if `pip` was installed with `easy_setup`.
