vim2pygments
============

Convert vim color schemes to [pygments][pygments] styles.

Usage - TL;DR
-------------

    $ python vimpygments.py molokai.vim > molokai.py
    $ hg clone http://bitbucket.org/birkenfeld/pygments-main pygments
    $ cd pygments
    $ cp ../molokai.py pygments/styles/molokai.py
    $ ./pygmentize -S molokai -f html -a .highlight > molokai.css

Usage - the long version
------------------------

Recently, I have grown to love [pygments][pygments].  It gives you syntax
highlighting in the browser without heavy Javascript files.  It supports just
about any programming language on the planet and it's just plain awesome.  The
only thing that it's lacking is good color schemes.  It comes with a dozen
themes that will certainly do the trick, but if you're used to looking at
pretty code in your favorite editor, the code examples on your website will
look a little dull.

I'm going to go out on a limb here and assume you have a favorite colorscheme.
I found a script that will turn a vim colorscheme into a Pygments theme.  It
didn't work perfectly out of the box so I patched it.  Copy your vim
colorscheme to the same directory as the script and run it like so:

    $ python vimpygments.py molokai.vim > molokai.py

This will produce a Python file containing a simple style class that Pygments
can use. Next step is to download Pygments:

    $ hg clone http://bitbucket.org/birkenfeld/pygments-main pygments

And then you will install your new theme:

    $ cd pygments
    $ cp ../molokai.py pygments/styles/molokai.py

OK, now for the fun part. We will use Pygments to generate the CSS file that
you will then use on your website:

    $ ./pygmentize -S molokai -f html -a .highlight > molokai.css

If you are a TextMate user, you might be able to get your favorite theme done,
too. A lot of popular Vim colorschemes are inspired by TextMate. Sunburst,
mustang and idle fingers come to mind. Just find a Vim version and you're good
to go.

[Original blog post][post]

Credits
-------

Original script by Armin Ronacher, patched by me.

License
-------

BSD licensed

[pygments]: http://pygments.org/
[post]: [http://honza.ca/2011/02/how-to-convert-vim-colorschemes-to-pygments-themes](http://honza.ca/2011/02/how-to-convert-vim-colorschemes-to-pygments-themes)
