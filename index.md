---
layout: page
title: Inbucket
tagline: Simple disposable webmail system
---
{% include JB/setup %}

Inbucket is an email testing service; it will accept messages for any email
address and make them available to view via a web interface.

It allows web developers, software engineers and system administrators to
quickly see the emailed output of ther applications.  No per-account setup is
required! Mailboxes are created on the fly as mail is received for them, and
no password is required to browse the content of the mailboxes.

Inbucket has a built-in SMTP server and stores incoming mail as flat files on
disk - no external SMTP or database daemons required.

Inbucket in action: [Screenshots]({{ BASE_PATH }}/screenshots.html)

Features
--------

SMTP features:

 * Receive and store E/SMTP messages
 * Purge messages after a configurable amount of time
 * Optional load test mode; messages are never written to disk

Web interface features:

 * List messages in a mailbox
 * Displays text content of a particular message
 * Displays source of a message (headers + body text)
 * Displays HTML version of a message (in a new window)
 * List MIME attachments with buttons to display or download
 * Delete a message

Not implemented yet:

 * Display inline attachments within HTML email

Development Status
------------------

Inbucket is currently beta quality: it works but is not well tested.

Please check the [issues list](https://github.com/jhillyerd/inbucket/issues?state=open)
for more details.

Installation
------------

You will need a functioning [Go installation][1] for this to work. 

Grab the Inbucket source code and compile the daemon:

    go get -v github.com/jhillyerd/inbucket

Edit etc/inbucket.conf and tailor to your environment.  It should work on most
Unix and OS X machines as is.  Launch the daemon:

    $GOPATH/bin/inbucket $GOPATH/src/github.com/jhillyerd/inbucket/etc/inbucket.conf

By default the SMTP server will be listening on localhost port 2500 and
the web interface will be available at [localhost:9000](http://localhost:9000/).

There are RedHat EL6 init, logrotate and httpd proxy configs provided.

About
-----
Inbucket is written in [Google Go][1].

Inbucket is open source software released under the MIT License.  The latest
version can be found at https://github.com/jhillyerd/inbucket

[1]: http://golang.org/

