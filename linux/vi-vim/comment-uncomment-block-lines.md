
# https://stackoverflow.com/questions/947897/block-comments-in-a-shell-script

In vi/vim, to comment out lines 10-100:

<ESC>
:10,100s/^/#/


Uncomment:

<ESC>
:10,100s/^#//
