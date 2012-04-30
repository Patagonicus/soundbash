# SoundBash #

## Description ##

SoundBash extracts the streaming URLs from [SoundCloud](http://soundcloud.com/).
Either single track links or pages containing multiple tracks such as user pages
or search results can be passed.

## Usage ##

The most basic form of using soundbash is passing SoundCloud URLs to the script.
It will then extract up to ten pages of streaming URLs from each link. You can
change that number using the ``-m`` flag. If 0 or a negative number is passed,
soundbash will extract all URLs it can find.

If you want the tracks uploaded by a user, use ``-u username`` and
``-f username`` for his or her favorites. You can extract URLs from tracks
posted to a group with ``-g group``. The commands can be mixed. Please note
that ``-m`` only works for the URLs coming afterwards.

## Examples ##

Extract the link for a single track:

	soundbash "http://soundcloud.com/silvahound/silva-hound-martyr-original"

Extract the links from the first two pages of a user’s tracks:

	soundbash -m 2 "http://soundcloud.com/silvahound/tracks"

Or shorter:

	soundbash -m 2 -u silvahound

Even shorter, but not quite as clear:

	soundbash -mu 2 silvahound

You can also mix:

	soundbash -m 2 -f patagonicus -m 4 -g trance "http://soundcloud.com/powerlifter/tracks"

This will extract the first two pages of patagonicus’ favorites and the first
four pages of the trance group and Powerlifter’s tracks. The short (and
unreadable) version would be:

	soundbash -mfmg 2 patagonicus 4 trance "http://soundcloud.com/powerlifter/tracks"

## Note ##

The URLs always have the form
``http://media.soundcloud.com/stream/$ID?/$user/$track``. You can therefore
get the track page from an URL by replacing everything up to (and including)
the quotation mark with ``http://soundcloud.com``.
