vim2pygments
============

Convert vim color schemes to [pygments][pygments] styles.

Usage
-----

    $ python vim2pygments.py molokai.vim > molokai.py
    $ hg clone http://dev.pocoo.org/hg/pygments-main pygments
    $ cd pygments
    $ cp ../molokai.py pygments/styles/molokai.py
    $ ./pygmentize -S molokai -f html -a .highlight > molokai.css

More
----

You can read the full guide in the original blog [post][post].

Credits
-------

Original script by Armin Ronacher, patched by me.

License
-------

BSD licensed

[pygments]: http://pygments.org/
[post]: http://honza.ca/2011/02/how-to-convert-vim-colorschemes-to-pygments-themes/

