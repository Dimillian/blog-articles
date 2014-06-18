### It works out of the box

True story, I tried it. 

So you want to make a new shiny `Swift` project but you are worried about not be able to use all those awesome `Objective-C `libraries? Worry no more!

Apple did some clever things with Swift, you can use Objective-c code within a swift project, Xcode will automatically generate a Swift "header" for the imported cod so you can call the original function in your `Swift` code like if it was coded in `Swift` right from the beginning.

So let's create a new simple `Swift` project, a single view application for example:

{<1>}![image](http://f.cl.ly/items/2L0b1H0w0j003e213q2H/Screen%20Shot%202014-06-04%20at%2017.27.48.png)

{<2>}![image2](http://f.cl.ly/items/0d300x1p1Q0G0z33360V/Screen%20Shot%202014-06-04%20at%2017.28.08.png)


The first thing you want to do is enable the `Objective-c ` bridging header. In order to be able to use `Objective-c` code in `Swift`, you need to tell Xcode to use a bridging header, you'll import all your `Objective-C` headers in this file, once done, all the headers imported here will be exposed to your swift code. 

It's very simple to do that, `file => new file` and choose `Objective-C` source file, Xcode will then ask you if you want to enable the `Objective-c` bridging.

{<3>}![image3](http://f.cl.ly/items/3o0B1z3n180y3o3v3225/Screen%20Shot%202014-06-04%20at%2017.28.44.png)

Click yes, it'll create your source file alongside a .h. You can remove the source file you've created, we created it only for Xcode to automatically link the header and enable `Objective-C` within the project. We could have done it manually but hey, doing this offer the configuration for free.

{<4>}![image4](http://f.cl.ly/items/303L2T3U15271d2e0U0C/Screen%20Shot%202014-06-04%20at%2017.28.55.png)

Now create a `podfile`, add `pod 'AFNetworking'` for example, run a pod install. 
Then open your workspace, what you need to do is import the `AFNetworking.h` in the bridging header. Once you've done that, you can call `AFNetworking` code in `Swift`! 

[Example app & code](https://github.com/Dimillian/SwiftTests/blob/master/testApp/MainController.swift)


