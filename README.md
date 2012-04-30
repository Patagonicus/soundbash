# SoundBash #

SoundBash extracts the streaming URLs from [SoundCloud](http://soundcloud.com/).
Either single track links or pages containing multiple tracks such as user pages
or search results can be passed.

Appended to the URLs is, separated by a quotation mark, the path of the track
page. For example, for the streaming URL
``http://media.soundcloud.com/stream/AB0123456789?/foo/bar``, the track URL
would be ``http://soundcloud.com/foo/bar``.
