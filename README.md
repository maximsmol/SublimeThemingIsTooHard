# Forum post

After spending a moderate amount of time making my own ST theme, I can claim with some confidence that this is much harder than it has to be for one simple reason: *there is no tutorials or documentation*.

To address that issue, I am starting a project.
The idea is to create as complete a documentation on ST theming as possible. I think that sublime forum is the best place to do this, as there are *active* themers here, who have worked on some of the best and biggest themes available.

The tasks that I feel need to be completed are:

* Creating a list of all the class-names used in `.sublime-theme` files. With instructions on finding the customized UI element.
* Creating a list of all the attributes relating to each class-name. With descriptions of when the attribute is applied
* Creating a list of all the properties available for customization (`layer0.***`, `row_padding`, `fg`) by class-name. And a description of each property.
* Creating a list of all the other forum threads talking about this subject. [Example.](https://forum.sublimetext.com/t/sidebar-icons-in-themes/13119)
* Maintaining this or some other thread as a theming Q&A thread

# What is a ST theme?

A Sublime Text theme is a way to customize the appearance of ST's UI. That includes the side bar, the status bar, the file tabs etc.

# Contents

File / Folder | Description
------------- | -----------
default/ | contains the unzipped version of the "Theme - Default" package
attributes.md | contains a list of attributes relating to each class-name
classes.md | contains a list of all the currently known classes, used in `.sublime-theme` files
properties.md | contains a list of all the currently known properties, used in `.sublime-theme` files
threads.md | contains a list of all the forum threads, discussing on the same topic as this project
