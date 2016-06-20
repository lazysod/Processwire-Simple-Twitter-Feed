# README #

## Installing ##

1. Go to https://apps.twitter.com and set up your app, read only permissions is fine. 
2. Then edit /inc/config.php adding all required keys. 
3. Upload and install to processwire as normal. (*zip and upload via Admin area for best result*) 

## Usage ##
On the page you wish to use this on use something like:  
$tw = new twitterFeed;
$tweets = $tw->getTweets(your_Twitter_user_name_here);

You can control the ammount of tweets you pull by supplying a number. If no number is given it will grab the most recent tweet you posted.
EG: $tweets = $tw->getTweets(your_Twitter_user_name_here, 2);

It will then produce an array with the following.

* id (message id)
* source
* status
* time
* avatar
* screen_name
* profile_url
* real_name

You can then call other functions of the class to create links if you wish like:

* $tw->make_links($tweets['status']); - This will link all hashtags and @username's as well as any URLS the tweet might contain
* $tw->twitter_time($tweets['time']); - This will give a more twitter like time result based on the actual timestamp of the tweet. (eg: 1 hour ago)
from here you can style and control the output as you like this readme would normally document whatever steps are necessary to get your application up and running.

## Help ##
If at any time you want to display this help documentation call the help function **$tw->help();**