# Configuring bots

For all bots developed here, you must fill out fields `USERNAME`, `PASSWORD`, `CLIENT_ID`, and `CLIENT_SECRET`.

####To get the `CLIENT_ID` and `CLIENT_SECRET` settings:
1. Go [here](https://www.reddit.com/prefs/apps/)

2. Fill it out like [this](http://i.imgur.com/a9vK6iQ.jpg).

3. The values should then appear like [this](https://i.imgur.com/qugkV2e.png).

# Bot coding practices

* Using the `get_access_token()` and `get_praw()` functions which I use all the time (as opposed to the popular OAuth2Util) allows bot code to be run automatically, even in environments without a GUI/X.

* A good way for a bot to identify comments it made for a specific reason is to have the comments prefaced with a markdown comment. E.g.:

        [NO_LOCATION]:#
        Please enter a location into the body of your post.
 This allows a bot to know what it has and hasn't commented on and for what reasons, and is much cleaner than keeping a text file or, even worse, a global list within memory.
