Transparent proxy fork of pywb
==============================

The ``proxy-ia`` branch allows to run pywb as a `transparent proxy <https://httpwg.org/specs/rfc7230.html#rfc.iref.t.2>`_ (using the patch ``force-proxy.patch``).

In contrast to a `regular HTTP proxy server <https://httpwg.org/specs/rfc7230.html#rfc.iref.p.1>`_, a transparent proxy does not need to be configured on individual clients. Instead, it intercepts and handles regular HTTP connections on a network. The web archive can be made available locally, be hosted with a remote public web archiving service, or a mixture of both.

See the example configuration (``config.yaml``), which makes pywb run on TCP port 80 (HTTP's default port) and transparently forward all HTTP requests to the Wayback Machine requesting a pre timestamp.

Adding transparent proxy mode to pywb makes it possible to serve web archives to clients in emulation environments without having to make changes to their originally preserved state, as well as software that doesn't allow to change proxy settings or doesn't respect system-wide proxy configuration.

Use cases:

* Enrich emulation environments with a contemporaneous "ambient" web, including resources required to install legacy software

* Provide fallback web archives containing external resources in addition to a server that has been completely preserved

* Connect preserved software with specific web archives, such as online user guides

* If the web archive represents the main artifact of a software object, load it into an emulation environment similar to a disk image

Recommended to be used together with `fake-dns <https://gitlab.com/emulation-as-a-service/experiments/fake-dns/>`_.


Webrecorder pywb 2.3
====================

.. image:: https://travis-ci.org/webrecorder/pywb.svg?branch=master
      :target: https://travis-ci.org/webrecorder/pywb
.. image:: https://ci.appveyor.com/api/projects/status/qxnbunw65o929599/branch/master?svg=true
      :target: https://ci.appveyor.com/project/webrecorder/pywb/branch/master
.. image:: https://codecov.io/gh/webrecorder/pywb/branch/master/graph/badge.svg
      :target: https://codecov.io/gh/webrecorder/pywb

Web Archiving Tools for All
---------------------------

`View the full pywb documentation <https://pywb.readthedocs.org>`_

**pywb** is a Python (2 and 3) web archiving toolkit for replaying web archives large and small as accurately as possible.
The toolkit now also includes new features for creating high-fidelity web archives.

This toolset forms the foundation of Webrecorder project, but also provides a generic web archiving toolkit
that is used by other web archives, including the traditional "Wayback Machine" functionality.


New Features
^^^^^^^^^^^^

The 2.x release included a major overhaul of pywb and introduces many new features, including the following:

* Dynamic multi-collection configuration system with no-restart updates.

* New recording capability to create new web archives from the live web or other archives.

* Componentized architecture with standalone Warcserver, Recorder and Rewriter components.

* Support for Memento API aggregation and fallback chains for querying multiple remote and local archival sources.

* HTTP/S Proxy Mode with customizable certificate authority for proxy mode recording and replay.

* Flexible rewriting system with pluggable rewriters for different content-types.

* Standalone, modular `client-side rewriting system (wombat.js) <https://github.com/webrecorder/wombat>`_ to handle most modern web sites.

* Improved 'calendar' query UI, grouping results by year and month, and updated replay banner.


Please see the `full documentation <https://pywb.readthedocs.org>`_ for more detailed info on all these features.


Installation
------------

To run and install locally you can:

* Install with ``python setup.py install``

* Run tests with ``python setup.py test``

* Run Wayback with ``wayback`` (see docs for info on how to setup collections)

* Build docs locally with:  ``cd docs; make html``. (The docs will be built in ``./_build/html/index.html``)


Consult the local or `online docs <https://pywb.readthedocs.org>`_ for latest usage and configuration details.


Contributions & Bug Reports
---------------------------

Users are encouraged to fork and contribute to this project to keep improving web archiving tools.

A few key features are high on list of priorities, but have not yet been implemented, including:

* Url Exclusion System

* UI Improvements

If you are interested in contributing, especially to any of these areas, please let us know!

Otherwise, please take a look at `list of current issues <https://github.com/webrecorder/pywb/issues>`_ and feel free to open new ones about any aspect of pywb, including the new documentation.


