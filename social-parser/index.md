#Social Parser
	
PHP class able to parse latest posts from facebook pages, youtube users, twitter users and google plus users.
This Class has four main methods, one for each social networks, and other two auxiliary methods necessary in order to accomplish some operations. The idea is to retrieve a given number of posts or status updates from the social networks listed above. So each method will have two attributes : the username or user id from who we want to parse status updates and the number of posts we want to retrieve.

To read the entire development explained step by step go [here](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

	author Andrea Morone
	version 1.0
	last update 9/7/2014

#####NotesTwitter and Google+ need API integration to work. So if you don't know how to create and obtain your API KEY from twitter or google, please refer to this [guide](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

##Getting Started
First of all you need to download  the class itself and then include it in you project.
```php
//Put this line at the beginning of your file to include Social Parser Class
include_once('path/to/class/socialparser.php');
```
Then you need to set your API KEY for Twitter and Google in socialstream.php. If you don't know how to create and obtain your API KEY from twitter or google, please refer to this [guide](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

##Implementation
Use this class is very easy, just call the method you need and pass it the username of the user from who you want to parse updates and the number of updates. Then you have to iterate trough the array to retrieve single post.  
That's it.	
```php
	$socialparser = new Socialparser();  
	$facebook_posts = $socialparser->facebook('FACEBOOK PAGE ID',NUMBER OF POSTS);  
	$youtube_videos = $socialparser->youtube('YOUTUBE USERNAME',NUMBER OF POSTS);  
	$tweets =  $socialparser->twitter('TWITTER USERNAME',NUMBER OF POSTS);  
	$google_posts = $socialparser->google('GOOGLE PLUS ID',NUMBER OF POSTS);
```

##Methods
#####Facebook Method
Return type **array()**

- title- link- author
- publishedDate
- contentSnippet
- content
- categories -> *array*

Attribute 

- $id = Facebook ID page
- $num = the number of posts to retrieve


```php
	facebook();
```

##Live Demo
If you want to see a live implementation of this class, you can see [here](http://projects.andreamorone.com/socialparser/).

##Comments