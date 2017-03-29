# IEEE-NSIT for iOS

### Download from App Store
[![](https://owncloud.org/wp-content/themes/owncloudorgnew/assets/img/clients/buttons/appstore.png)](https://appsto.re/in/Z67Phb.i)

IEEE-NSIT Student Branch works to create an atmosphere of technical excellence for the students. It aims at helping students in building an aptitude towards applying engineering in daily life by learning ways to use the latest technology on offer. Through this app, students can remain informed about events and news pertaining to IEEE-NSIT.

## Features
### 1. Home
This is the home page of the app - shows posts from IEEE NSIT's facebook page. Tap on a post to view text and the associated image. 

<img src = "https://github.com/Swapnil52/ieeeNSIT/blob/master/ieeeNSIT/home.PNG" height = 300>
          <img src = "https://github.com/Swapnil52/ieeeNSIT/blob/master/ieeeNSIT/post.PNG" height = 300>
          
The blur effect shown above works by taking a low resolution screenshot just as the user taps on a cell, and presenting the new controller modally - with the screenshot masked by a UIVisualEffectView instance. 

### 2. Events
Shows a collection of upcoming events organised by IEEE NSIT. Uses a custom card based interface - swipe between cards to view events, pull down to refresh and tap on the date to add the event to your calendar.

<img src = "https://raw.githubusercontent.com/Swapnil52/ieeeNSIT/master/ieeeNSIT/events.PNG" height = 300>

### 3. Gallery
Shows images posted on IEEE.org's Facebook page. Uses a UICollectionView for displaying thumbnails and IDMPhotoBrowser to display selected images and their captions.

<img src = "https://raw.githubusercontent.com/Swapnil52/ieeeNSIT/master/ieeeNSIT/gallery.PNG" height = 300>

### 4. IEEE ID
Acts as a substitute for payment slips. Instead of carrying worn out slips which can easily be misplaced, IEEE members can log in with their registered mobile number, and present the generated ID at events. Users not registered with IEEE can send an email to ieeensit2016@gmail.com, or a message on Facebook.

<img src = "https://github.com/Swapnil52/ieeeNSIT/blob/master/ieeeNSIT/id.PNG?raw=true" height = 300>

### 5. Push Notifications
Support for push notitications has been added. When a user installs the app for the first time, the device token generated by APNS is uploaded to our database.
For pushing notifications, firstly, a fetch request is made to the Facebook graph API using the following URL:
```
https://graph.facebook.com/(Insert Page ID)/posts?limit=1&fields=id&access_token=(Insert API Key)
```
This returns the ID of the newest post on the page. Comparing it with the already stored ID, the server can decide whether to push a notification.

<img src = "https://raw.githubusercontent.com/Swapnil52/ieeeNSIT/master/ieeeNSIT/pushNotifications.PNG" height = 300>

## Libraries used
### 1. SDWebImage
Popular asynchronous image downloading library (https://github.com/rs/SDWebImage)

### 2. IDMPhotoBrowser
Versatile library to show images (with captions) and albums in iOS apps (https://github.com/thiagoperes/IDMPhotoBrowser)

## APIs used
### 1. Facebook Graph api for page posts
```
https://graph.facebook.com/(Insert Page ID )/posts?limit=20&fields=id,full_picture,picture,from,shares,attachments,message,object_id,link,created_time,comments.limit(0).summary(true),likes.limit(0).summary(true)&access_token=(Insert API Key)
```
To fetch JSON data of a particular page, plug in the page id in the format shown above and you're good to go! For example, the page ID of IEEE NSIT is 278952135548721

### 2. Facebook Graph api for events
```
https://graph.facebook.com/v2.5/(Insert Page ID)/events?limit=5&fields=name,start_time,description,cover&access_token=(Insert API Key)
```
Returns JSON data containing recent and upcoming events organised by IEEE NSIT.

## How to contribute?
You'll need:
- A mac with OSX El Capitan or later. Don't fret if you don't have a mac! You can run OSX on your Windows PC using Virtual Box. If you like tinkering with your computer, dual boot via Hackintosh
- To learn an iOS programming language(Obj-C or Swift)from a popular online course or book like 'The Big Nerd Ranch Guide'. (This project has been written using Swift 2.2)
- Install Xcode
- To build, fork the repository or download the zip to your computer. If you get a cocoapod error (when a certain dependency can't be found), run pod install for the pods mentioned above and you'll be good to go!

## Other repositories:
- Android : [Ajay Chowdhary](https://github.com/AjayChowdhary/IEEENSIT)
- Push Notifications : [Siddharth Nijhawan](https://github.com/fgethell/ios-push-notifications)

## Contact information
This repository is written and maintained by Swapnil Dhanwal.
E-mail *swapnildhanwal@hotmail.com*
