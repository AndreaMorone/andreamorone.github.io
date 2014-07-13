#Social Parser
	
PHP class able to parse latest posts from facebook pages, youtube user updates, user tweets and google plus user updates.
This Class has four main methods, one for each social network, and other two auxiliary methods necessary in order to accomplish some operations. The idea is to retrieve a given number of posts or status updates from the social networks listed above. So each method will have two attributes : the username or user id from who we want to parse status updates and the number of posts we want to retrieve.

To read the entire development explained step by step go [here](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

	author Andrea Morone
	version 1.0
	last update 12/7/2014

#####NotesTwitter and Google+ need API integration to work. So if you don't know how to create and obtain your API KEY from twitter or google, please refer to this [guide](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

##Getting Started
First of all you need to download  the class itself and then include it in you project.
```php
//Put this line at the beginning of your file to include Social Parser Class
include_once('path/to/class/socialparser.php');
```
Then you need to set your API KEY for Twitter and Google in socialstream.php. If you don't know how to create and obtain your API KEY from twitter or google, please refer to this [guide](http://c0desn1p.com/retrieve-latest-posts-from-social-networks-with-php/).

##Implementation
Use this class is very easy, just call the method you need and pass it the username of the user from who you want to parse updates and the number of updates. Then you have to iterate through the array to retrieve single post.  
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
	facebook($id,$num);
```
#####Youtube Method
Return type **array()**

- title- id = videoID

Attribute 

- $id = Youtube Username
- $num = the number of posts to retrieve


```php
	youtube($id,$num);
```
#####Twitter Method
Return type **array()**

- text- image

Attribute 

- $id = Twitter Username
- $num = the number of posts to retrieve


```php
	twitter($id,$num);
```
#####Note
Remember to set the API KEY

#####Google Method
Return type **array()**

- title- url = url of post
- image

Attribute 

- $id = Google Plus Username or ID
- $num = the number of posts to retrieve


```php
	google($id,$num);
```
#####Note
Remember to set the API KEY

##Example

Example of the implementation could be the following. You can see it live above.

```html
<?php  
include_once('socialparser.php');
$socialparser = new Socialparser();
$facebook_posts = $socialparser->facebook('146610298732369',5);
$youtube_videos = $socialparser->youtube('SapienzaRoma',5);
$tweets =  $socialparser->twitter('SapienzaRoma',5);
$google_posts = $socialparser->google('+Ferrari',5);
?>
<!doctype html>
<html>
<head>
	<meta charset="UTF-8" />
	<title>PHP - Social Parser</title>
</head>
	<style>
		body {
		padding: 0px 10% 0px 10%;
		}
		body div {
			width: 20%;
			padding: 10px;
			float: left;
		}
		body div img {
			max-width: 100%;
		}
		ul {
			list-style: none;
			padding: 0px;
		}
		iframe {
			width: 100%    !important;
			height: auto   !important;
		}
	</style>
<body>
	<div>
		<h2>Facebook</h2>
		<ul>
			<? foreach($facebook_posts as $fb){ ?>
				<li>
					<p><? echo $fb['title'] ?></p>
					<p><? echo $fb['content'] ?></p>
				</li>
				<hr>
			<? } ?>
		</ul>
	</div>
	<div>
		<h2>Youtube</h2>	
		<ul>
			<? foreach($youtube_videos as $yt){ ?>
				<li>
					<p><? echo $yt['title'] ?></p>
					<iframe id="ytplayer" type="text/html" src="http://www.youtube.com/embed/<? echo $yt['id']; ?>?autoplay=0" frameborder="0"/></iframe>
				</li>
				<hr>
			<? } ?>
		</ul>
	</div>
	<div>
		<h2>Twitter</h2>	
		<ul>
			<? foreach($tweets as $tw){ ?>
				<li>
					<p><? echo $tw['text'] ?></p>
					<img src="<? echo $tw['image'] ?>"/>
				</li>
				<hr>
			<? } ?>
		</ul>
	</div>
	<div>
		<h2>Google</h2>	
		<ul>
			<? foreach($google_posts as $goog){ ?>
				<li>
					<p><? echo $goog['title'] ?></p>
					<img src="<? echo $goog['image'] ?>"/>
				</li>
				<hr>
			<? } ?>
		</ul>
	</div>
</body>
</html>
```

##Live Demo
If you want to see a live implementation of this class, you can see [here](http://projects.andreamorone.com/?project=PHPSocialParser).

##Comments