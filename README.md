# tdd-w-python
working through the oreilly tdd with python book (http://www.obeythetestinggoat.com/)

See https://github.com/hjwp/book-example for the author's proper repo, and http://www.obeythetestinggoat.com/ for the book's page.

Started work on this in summer of 2015, but only completed the first 6 chapters. Starting again in Winter 2015/2016 to try to complete.

The main points of the book I'm interested in are learning TDD through practice, and implementing django.

# Jenkins CI

For my CS178 final project I was trying to apply continuous integration to automate testing of a python project from a book I've been working through in my free time. I should be able to run my specific tests and leave the remaining lionshare of the tests to jenkins. This would include how to run headless selenium tests of pages using xvfb.

I did manage to achiveve running the tests headlessly, but I've been unable to get the screenshotting to work. I also had to include pyvirtualdisplay to control my virtual displays, but this has lead to them not displaying on my local machine (which I don't necessarily want).

I will also need to revisit the setup of the javascript runners as I haven't reached that stage of the book/website.

## Setting up and running

### Required packages
Setting up on an existing Jenkins system with git installed requires firefox, python3, python virtual environment, and xvfb (x virtual frame buffer)

    sudo apt-get install firefox python3 python-virtualenv xvfb

###Plugins This also requires the jenkins plugins for

* git
This should already be installed based on previous coursework.
* Shining Panda
* xvfb

From there you need to point to your python and xvfb installs. In jenkins under the Manage Jenkins->Configure System list you should have ann option for python installations. Python3 should be under /usr/bin/python3 by default. Xvfb directory should be just /usr/bin

From there the jenkins job xml should be able to be dropped into your jobs directory and be able to run either from polling or via build now.
