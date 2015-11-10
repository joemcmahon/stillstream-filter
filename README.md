# stillstream-filter
***Filter GMVault-downloaded artist signups to build a DJ "okay to play" list***

StillStream, as a zero-profit (actually a negative-profit) Internet radio station, has come to a compromise
with our artists: we ask them to sign a waiver that allows us to play their music without making payments to
SoundExchange. In exchange, we add them to our library, which is played 24 hours a day, either by our DJ robot,
Wallace, or by our individual human DJs.

(StillStream also does live streaming and performances, sometimes by our DJs, sometimes by other artists. We've
even streamed a Steve Roach concert live via iPad!)

We have had several signup programs over the years; the common feature they share is that they mail out a copy of
the signup form to the artist and to the StillStream administrators. We've used various methods of tracking signups
so our DJs know what they can play (and so we have a record), but all of them one way or another have boiled down to
"read the email and compile a list".

We had a transition from a custom PHP website to Wordpress, and in the process we lost the script that updated our
database from the script, and ended up with a backlog of several hundred emails that needed to be processed, in
several different formats.

I eventually hit on the idea of tagging the mails with a Gmail label, and then using [gmvault](http://gmvault.org)
to download only[1] the mails I wanted, then wrote this script to filter them and produce a list of the people
who signed up and the artists or projects they represent (some artists are involved in multiple projects, but may
not want to release all of their music to StillStream).

**Using it**

Most people probably can't use this script as it stands, as it is very much a special-purpose script; however, I'm
putting it up here as an example of data-munging a very messy input dataset. I'm planning on extending the script
to output SQL to allow us to rebuild the main artists database again; this would allow us to provide better access
to the artists and their websites for our listeners.

[1] I actually ended up with a few extraneous emails that had to be filtered out; the code now specifically looks for
the formats I expect and throws anything else away.
