# KeylessTwitter
A small module I was working on for a friend's project that allows (very) basic interaction with Twitter without using an API key
# Features
- [x] Signing in
- [x] Sending simple tweets
- [x] Sending tweets with media
- [x] Sending tweets with more than one image (media item)
- [ ] Direct Messages
- [ ] Events
- [ ] Notifications
- [ ] A lot more...
# Usage
Starting usage
```
Twitter mainTwitter = new Twitter("USERNAME", "PASSWORD"); // Creates a new Twitter with the specified credentials
mainTwitter.tryLogin(); // Logs in to the Twitter account (returns true or false depending on login status)
```
Sending a tweet
```
mainTwitter.Tweet("Hello world! #KeylessTwitter"); // Tweets the specified tweet. Remember, there is a 140 character limit, which will cause a 403 if exceeded
```
Tweeting an image (by URL)
```
// The general idea is that they use byte[], which allows for you to load from a file if needed
mainTwitter.TweetImage(new WebClient().DownloadData("http://example.com/my_twitter_picture.jpg"), "Check out this image!"); // Tweets from said URL
```
Tweeting images (by URLs)
```
mainTwitter.TweetImage(new byte[][] { new WebClient().DownloadData("http://example.com/my_twitter_picture.jpg"), new WebClient().DownloadData("http://example.com/my_other_picture.jpg") }, "Check out these images!"); // Tweets from the specified URLs
```
