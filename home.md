#WALLBID DOCUMENTATION

###OVERVIEW

Wallbid is a social stream platform where everyone can create wall of interest and share with friends.

###Technical notes

####Layout
The entire website is built on *twitter bootstrap v3*
<http://getbootstrap.com/>

Some elements layout are loaded from *controller* **constructor** (ex. *sidebar* or *layout*)
```php
$car = "";
	if($car == 'lusso'){
		$car="ferrari";
	}```
Layout consist of `3` main components:

- header 
```html
<strong>Hola, mundo</strong>
```
- body
- footer

Some modals are loaded from *modal views*

####Encryption
Password and other elements are encrypted with *bcrypt* library <https://github.com/dwightwatson/codeigniter-bcrypt>. The *databse* table must be **`128 VARCHAR`** 

####Messagges 
Error messagges and information are handled by the library *codeigniter messagges* <https://github.com/darkhouse/codeigniter-message>

[Button >](http://url.com/ "Title")


####ATTENTION
 - Wall image and wall preview image are different
 - like or follow if clicked rapidly dosen't working well

Function `display` modified to use with jQuery notification:

`//echo $this->get($group, $wrapper);
		$message_ = $this->get($group, $wrapper);
		return $message_;`
		
	LINE 53 - Library Message.php

####Uploads

#####Profile pictures
Are inside `uploads/profile-pictures`. On database the field is on `user` table and is `picture_profile`, in session the variable is `picture-profile` 

#####Wall pictures

##jQuery Plugin

####jQuery Validate

####jQuery Scrooltofixed

####jQuery Form

####jQuery Switch

####jQuery Grid-a-Licious

####jQuery Social Stream

####jQuery OWL Notification
Icon from <http://www.fontsquirrel.com/fonts/entypo>

##BUG OR NOT WORKING WELL
- after sign in *create wall* not working


##API

####update_wall_active
**type post** update the status o wall (active or deactive)

