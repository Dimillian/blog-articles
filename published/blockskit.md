I recently started a new/side iOS application alongside my main one. I decided to write it with the less code possible, so I started digging into my notes and searching for all the cool libraries I starred for later use. 
(Yeah integrating a library which change your codestyle late into a projet is generally a bad idea).

I'll pass on [ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa), [ObjectiveSugar](https://github.com/supermarin/ObjectiveSugar) and other libraries I integrated in this new project and jump on to [BlocksKit](https://github.com/pandamonia/BlocksKit)

This little marvel provide a lot of functions that are usually called through `delegate`, and transform them into blocks. 
In a lot of cases, blocks are a lot better than `delegate`, because it's more compact. When using an `UIAlertView` you want to be able to read the call to action of both buttons after the declaration. 
Now you can, you don't need to suscribe to a delegate and implement a function a few lines below.

All functions from blocksKit are prefixed with `bk_` which is cool because you can easily list every functions available from BlocksKit on an object. Also it won't conflict with [ObjevtiveSugar](https://github.com/supermarin/ObjectiveSugar) for example, as it duplicate some functions.

I mostly use the `UIKit` extension at the moment, it provice blocks for UIAlertView, UIActionSheet, UIButton and more. 

If you begin a new application I strongly encourage you to use the Blocks syntax, so make your own categories, or use BlocksKit. 
For external readers and contributors to your code, it's much more consise and readble. 