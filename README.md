# Configuring bots

For all bots developed here, you must fill out fields `USERNAME`, `PASSWORD`, `CLIENT_ID`, and `CLIENT_SECRET`. To get the `CLIENT_ID` and `CLIENT_SECRET` settings, go [here](https://www.reddit.com/prefs/apps/) with your bot account and fill it out like [so](http://i.imgur.com/a9vK6iQ.jpg).


# Bot coding practices

* Using the `get_access_token()` and `get_praw()` functions which I use all the time (as opposed to the popular OAuth2Util) allows bot code to be run automatically, even in environments without a GUI/X.

* A good way for a bot to identify comments it made for a specific reason is to have the comments prefaced with a markdown comment. E.g.:

        [NO_LOCATION]:#
        Please enter a location into the body of your post.
 This allows a bot to know what it has and hasn't commented on and for what reasons, and is much cleaner than keeping a text file or, even worse, a global list within memory.
