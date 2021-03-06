Rainbow Stream
--------------

.. image:: http://img.shields.io/pypi/dm/rainbowstream.svg?style=flat
   :target: https://pypi.python.org/pypi/rainbowstream

.. image:: http://img.shields.io/pypi/v/rainbowstream.svg?style=flat
   :target: https://pypi.python.org/pypi/rainbowstream

Terminal-based Twitter Client. Realtime tweetstream, compose, search ,
favorite … and much more fun directly from terminal.

This package is built on the top of `Python Twitter Tool`_ and `Twitter API`_.

Install
-------

You will need Python 2.7+ and pip.

.. code:: bash

    sudo pip install rainbowstream

or try with a virtualenv

.. code:: bash

    sudo pip install virtualenv # skip if you already have virtualenv
    virtualenv venv
    source venv/bin/activate # use the brand new virtualenv.
    pip install rainbowstream

Usage
-----

The stream
^^^^^^^^^^

Just type

.. code:: bash

    rainbow

and see your stream.

I shipped a feature which can display **tweet's images directly on terminal**.
You can try it with:

.. code:: bash

    rainbow -iot # Or rainbow --image-on-term

In the first time you will be asked for authorization of Rainbow Stream
app at Twitter. Just click the “Authorize access” button and paste PIN
number to the terminal, the rainbow will start.

The interactive mode
^^^^^^^^^^^^^^^^^^^^

While your personal stream is continued, you are also ready to tweet,
search, reply, retweet… directly from console. Simply type “h” and hit
the Enter key to see the help.

Input is in interactive mode. It means that you can use arrow key to
move up and down history, tab-autocomplete or 2 tab to view available
suggestion. Input history from previous run is available as well.

Here is full list of supported command:

**Explore Commands**

-  ``trend`` will show global trending topics. ``trend US`` will show
   trends in United States while ``trend JP Tokyo`` will show trends in
   Tokyo/Japan.

-  ``home`` will show your timeline. ``home 10`` will print exactly 10
   tweets.

-  ``mentions`` will show mentions timeline. ``mentions 7`` will show 7
   mention tweets.

-  ``whois @dtvd88`` will show profile of @dtvd88.

-  ``view @mdo`` will show @mdo ’s timeline. ``view @dmo 9`` will print
   exactly 9 tweets.

-  ``s #noah`` will search the word *‘noah’*. Result will come back with
   highlight.

**Tweet Commands**

-  ``t the rainbow is god's promise to noah`` will tweet exactly *‘the
   rainbow is god’s promise to noah’*.

-  ``rt 12`` will retweet the tweet with *[id=12]*. You can see id of
   each tweet beside the time.

-  ``allrt 12 20`` will list 20 newest retweets of the tweet with *[id=12]*. If the number of retweets is not specified, 5 newest retweets will be listed instead.

-  ``rep 12 Really`` will reply *‘Really’* to the tweet with *[id=12]*.

-  ``fav 12`` will favorite the tweet with *[id=12]*.

-  ``ufav 12`` will unfavorite tweet with *[id=12]*.

-  ``del 12`` will delete tweet with *[id=12]*.

-  ``show image 12`` will show the image in tweet with *[id=12]* in your
   OS’s image viewer.

**Direct Messages Commands**

-  ``inbox`` will show inbox messages. ``inbox 7`` will show newest 7
   messages.

-  ``sent`` will show sent messages. ``sent 7`` will show newest 7
   messages.

-  ``mes @dtvd88 hi`` will send a ``hi`` message to @dtvd88.

-  ``trash 5`` will remove message with *[message\_id=5]*

**Friends and followers Commands**

-  ``ls fl`` will list all your followers (people who are following
   you).

-  ``ls fr`` will list all your friends (people who you are following).

-  ``fl @dtvd88`` will follow @dtvd88.

-  ``ufl @dtvd88`` will unfollow @dtvd88.

-  ``mute @dtvd88`` will mute @dtvd88.

-  ``unmute @dtvd88`` will unmute @dtvd88.

-  ``muting`` will list muting users.

-  ``block @dtvd88`` will block @dtvd88.

-  ``unblock @dtvd88`` will unblock @dtvd88.

-  ``report @dtvd88`` will report @dtvd88 as a spam account.

**Switching Stream Commands**

-  ``switch public #AKB48`` will switch current stream to public stream
   and track keyword ``AKB48``

-  ``switch public #AKB48 -f`` will do exactly as above but will ask you
   to provide 2 list:

   ``Only nicks`` decide what nicks will be include only.

   ``Ignore nicks``\ decide what nicks will be exclude.

-  ``switch public #AKB48 -d`` will apply filter to *ONLY\_LIST* and
   *IGNORE\_LIST*. You can setup 2 list above at ``config.py``

-  ``switch mine`` will switch current stream to personal stream. ``-f``
   and ``-d`` will work as well.

**Smart shell**

- Put anything to terminal, the app will try to eval and display result as a python interactive shell.

  + ``142857*2`` or ``101**3`` like a calculator.
  + Even ``cal`` will show the calendar for current month.
  + Put ``order_rainbow('anything')`` or ``random_rainbow('wahahaha')`` will make more fun :)

**Screening Commands**

-  ``theme`` will list available themes. ``theme monokai`` will apply *monokai*
theme immedaitely.

-  ``h`` will show the help.

-  ``c`` will clear the screen.

-  ``q`` will quit.

Available commands are listed in `Read The Docs`_.

Theme customization
^^^^^^^^^^^^^^^^^^^

Rainbow Stream is shipped with some default themes. 
You can either change theme by ``theme`` command or create your favorite one.

Theme’s screenshot:

.. figure:: https://raw.githubusercontent.com/DTVD/rainbowstream/master/screenshot/themes/Monokai.png
   :alt: monokai

.. figure:: https://raw.githubusercontent.com/DTVD/rainbowstream/master/screenshot/themes/Solarized.png
   :alt: solarized

For detaile information, see `theme usage and customization`_.


.. _Python Twitter Tool: http://mike.verdone.ca/twitter/
.. _Twitter API: https://dev.twitter.com/docs/api/1.1
.. _theme usage and customization: https://github.com/DTVD/rainbowstream/blob/master/theme.md
