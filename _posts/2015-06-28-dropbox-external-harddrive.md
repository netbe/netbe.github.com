I recently purchased a Dropbox account with 1TB. THe idea is to use it to ~~sync~~ backup my data on all my devices (iPhone, iPad, MacBook Air), especially photos/videos.

One issue I have is the lack of space on the Mac (128GB), so it is not possible to store my new pics on it. Moreover, I have a 60GB ~~iPhoto~~ Photos library. It would be nice to back it up also to dropbox in case my harddrive gets broken or stolen.

## Problem

With Dropbox, you cannot specify an external location like harddrive easily nor without consequences. You could have a symlink in your Dropbox folder which points to the external harddrive, so the content is indeed backed up to Dropbox.

But when the harddrive gets disconnected, your content will be deleted from Dropbox (there are no files present anymore).

## Solution

* use a second dropbox instance application, [see how here](http://lifehacker.com/5971204/run-multiple-dropbox-accounts-on-one-computer)
* this application has its configuration file on the external harddrive
* it uses selective sync

Two effects:

* can't launch the application without the harddrive connected
{% picture no-harddrive.png alt="no harddrive connected" %}

* can't unmount the harddrive before quitting the app
{% picture harddrive-eject.png alt="can't unmount" %}

That way your data will not get erase when you unmount your hardrive or at least get a warning.

## What about iCloud?

I did try iCloud for less than a month. Here's the pros and cons:

### Pros

* Easy to setup

### Cons

* Slow to backup
* Can't see the space occupied on the device
* Don't know when files are finally backed up
