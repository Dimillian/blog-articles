are awesome. 

### For real!

I played with the API a bit, this is really simple, to do an hello world, just create a new project with Xcode 6, choose Swift (or maybe Objective-c :) ). 
Now you have a basic iOS 8 app, now choose file => new target, and in extension, choose whatever you want, the today extension is the most simple one for an hello world project.

{<5>}![image](http://f.cl.ly/items/1h1G2v1Z03263r3t3k2K/Screen%20Shot%202014-06-04%20at%2016.03.58.png)

Now you are setup, and ready to go, Xcode created the main view controller for your extension alongside a storyboard. 

{<6>}![image](http://f.cl.ly/items/2Q2S1R3m1W2Y0d0h270B/Screen%20Shot%202014-06-04%20at%2016.04.14.png)

Yes, this is true, a today extension is a true UIViewController subclass and respond to all the API you already know alongside some new one. 

If you build & go, you'll be able to add your extension to the notification center

{<7>}![image](http://f.cl.ly/items/0I2h1l003O2Y2e000r3A/Screen%20Shot%202014-06-04%20at%2016.10.51.png)

{<8>}![image](http://f.cl.ly/items/3K3b1B3O3C0P3S0W3S03/Screen%20Shot%202014-06-04%20at%2016.10.59.png)


I strongly suggest you to take a look at some of the [WWDC videos](https://developer.apple.com/videos/wwdc/2014/) session already available, especially "What's new in Cocoa Touch" and "Creating Extensions for iOS and OS X, Part1" if you want to have a solid grasp of what extensions are about. 

In short, to ship an extension you need an host app, you can ship any number of extensions of any kind with an application. You can't ship an extension without an application. As soon as the user will launch your app, he'll see the new extensions available at the bottom of the notification center and in the settings app. 

Also, extensions and your app are 2 completely separated binary, of course you can share code between them, reuse views etc... But your instance and process can't really communicate together. Not much more than you can communicate with system or other 3rd party app for exemple. You still share the same sandbox and app default, so I think it's largely enough. 

Anyway, this is really huge, it's not only widget, it's share action for Safari, photos and more.. Also you can expose content within your own app to let other "Action" extensions access and manipulate it.
 
If you want an actions that extract a movie metadata from an iTunes page or Amazon product page and send it to your app user library, well you can. Just make an action extension for Safari and remind the user to use it. Kinda like the "Add to reading list" button.

I also want to add that extensions are not nefarious for the end users, like the background multitasking Apple allowed recently, extensions widgets are controlled, killed and fired by the system. It won't have that much impact on performance and battery. I exept it to be really optimized. Your extension will be created as soon as the notification center appear and killed as soon as it disappear and that you task is done. 

I can't wait to see the first few iOS 8 apps with extensions. And of course, to make my own. 




