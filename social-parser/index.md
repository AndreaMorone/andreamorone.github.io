#Social Parser
PHP class able to parse latest posts from facebook pages, youtube users, twitter users and google plus users.
This Class has four main methods, one for each social networks, and other two auxiliary methods necessary in order to accomplish some operations. The idea is to retrieve a given number of posts or status updates from the social networks listed above. So each method will have two attributes : the username or user id from who we want to parse status updates and the number of posts we want to retrieve.

To read the entire development explained step by step go [here](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

	author Andrea Morone
	version 1.0
	last update 9/7/2014

##Getting Started
First of all you need to download  the class itself and then include it in you project.
```php
//Put this line at the beginning of your file to include Social Parser Class
include_once('path/to/class/socialparser.php');
```
##Implementation
	
```php
	$socialparser = new Socialparser();  
	$facebook_posts = $socialparser->facebook('FACEBOOK PAGE ID',NUMBER OF POSTS);  
	$youtube_videos = $socialparser->youtube('YOUTUBE USERNAME',NUMBER OF POSTS);  
	$tweets =  $socialparser->twitter('TWITTER USERNAME',NUMBER OF POSTS);  
	$google_posts = $socialparser->google('GOOGLE PLUS ID',NUMBER OF POSTS);
```
	
##Methods
###
##Comments