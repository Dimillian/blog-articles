**Disclaimer**: I play a lot of games, I used to play on console, but nowadays I mostly play on my Retina Macbook (which is also the computer I use for my job), because it's powerful, and OSX is not a barrier at all if you know what you're dealing with. I'll try to explain it what is like to play on OSX in this blog post.

#### OMG YOU PLAY ON MAC NOOB? GO BUY A REAL COMPUTER!

I would like to begin this post with the current state of gaming on a Mac in 2014, and also explain to you why some people think it's so bad.

It's bad because companies who makes AAA games don't care about Mac gaming and because Apple is late on graphic drivers.
AAA Mac games happen sometimes, for example Bioshock I, II, and III are available on Mac now, alongside the latest Lara Croft and some other AAA games too.

It's not bad because it's a rushed job (well kinda), it's bad because it uses the wrong technology. Then players try these games on Mac, see that performances are like 40% the performance of the same game under Windows, and here we are. Left alone with our cold metal Macbook and no games to play at 60 FPS.

That why we see raging users on forums who now think playing on Mac is a heresy and should never be done, only if you want the sky to fall on earth.

You have to understand that to port or make a game to run on OSX you have something like 2 options if the game is already running on Windows and already released.

1. The owner company can modify their engine to make it run natively on OSX. 

2. The owner company can ask an [external company](http://transgaming.com) to port the game for them. And the easiest way to do it is to make the game run under a Windows emulator (kinda, it's a translation layer in fact, more on that later).

Please note that the owner company can hire an external company to do point 1 and vice-versa.

What happen is the point 2 most of the time, it's cheaper (Okay I don't know about that part) and faster, and don't require to dive into existing huge codebase.

And this is the sad truth, and that's why most of the times, Mac game perform like craps, but let me explain why.

### About rendering engine

{<1>}![DirectX image](http://www.wired.com/images_blogs/photos/uncategorized/2008/07/23/directx.jpg)

Windows and OSX use a radically different API to translate graphics code to the GPU and then to the screen.
On Windows, programmers tend to make their game using the Direct3D (DirectX) interface, and this is normal. Microsoft make and promote this API really hard, and yes, it's actually very good. But it's limited to Windows only... But you can target most of the market by making games only for Windows.

It's still a fair point in 2014, but I want to believe that Valve and some other indie developers is in the process of changing everything. 
This year GDC have been amazing, the [Unreal Engine](https://www.unrealengine.com) editor is now available for Mac!

{<2>}![OpenGL Image](http://upload.wikimedia.org/wikipedia/en/8/8a/OpenGL_logo.jpg)

On Mac, if you wan to write a graphical Application, you must use **OpenGL** (**Open** Graphic Library). This is an API which allow you to display 2D and 3D graphics. The big bonus point of OpenGL is that it's **platforms** independent, it means that if you write an OpenGL application it'll be able to run on Windows, Linux and OSX (and other platforms too), with very minor modification for each platform.

But most of the games graphic engine are wrote using the DirectX API, because it's convenient, tools are here and it's what Microsoft support out of the box on Windows and Xbox. PS3/4 is another story, as it use a [modified version](http://scalibq.wordpress.com/2010/05/15/sony’s-playstation-3’s-main-graphics-api-is-not-opengl/) of OpenGL which is not really close to the classic OpenGL.

What most companies do is that they create some sort of middleware which translate the rendering code to DirectX or PS3 PNGL. Imagine is they included another [output to normal](https://github.com/ValveSoftware/ToGL) OpenGL (well even Apple use a slightly modified version of OpenGL).

###About Direct3D to OpenGL translation layer

To come back to the point 1 of my list, usually what happens is that the game is released on Mac using what is called a Windows translation layer. It's a middleware that translate every Windows API and Direct3D call and execute the correct corresponding OSX/OpenGL call. 

It doesn't sound bad if I said it like that, but first it's a middleware, so no matter what, It'll slow down what happen between your program and the metal, it adds a layer to your application after all.

But you'll also don't profit of platforms specific features and optimisations you could have made by writing true OpenGL code.
There is a really good article on The Porting Team community [here](http://portingteam.com/frontpage/_/community-articles/reviews/mac-gaming-is-native-always-better-r19). True thing, native games are not always faster that one using a translation layer. Yes, the game is still thinked Windows/DirectX first, and OpenGL later.
Blizzard and Valve are some of the only companies to make true OSX games. If you want to really play optimized and good games on Mac Portal 2 and Diablo 3 are a good start.

{<3>}![Feral logo](http://www.oneclickmac.com/wp-content/uploads/2012/09/Feral_Logo_OrangeBlack.png)

Most of AAA Mac games port are usually done by [Feral Interactive](http://feralinteractive.com) or [Apsyr](http://www.aspyr.com).
Games released from those companies are usually quite good, I can remember playing Bioshock and Borderlands on my old Macbook, it was really a good experience. I believe those companies write their own translation layer (Or maybe recode parts of the engine directly to OpenGL), the thing is, the game is still made for DirectX first and recoded/translated for OpenGL later.

There is another company called Transgaming, they have a product called [Cider](http://transgaming.com/cider).
Cider works much like Wine, it was initially created from a modified version of Wine. It's a commercial version of Wine, with some professional tools built-in to ease porting games.
Cider could have been good, but from what I've learnt and what I've tried, and it's not very up to date. 
While I see the improvements compared to 2 years ago, it still bad. Games released with Cider tend to be really slow and very limited in term of graphic settings available and performance.
It's a closed source middleware, which is only accessible if you license it to the parent company. Activision, EA, and some other companies contract with Transgaming, and Call of duty, and The Sims are not the best ported games available on OSX.

It's sad because there is also [Wine](http://www.winehq.org) which is evolving very vast lately. Wine is an open source Windows translation layer, and it's really easy to use and have a very active community around it.

To put what I said in perspective, I do Mac ports as a hobby, if I take a game released on Mac using Cider, and if I make the port myself using Wine, it'll usually run better and faster than the official port. It'll also take me no more than 30 minutes to do.
I don't know how much money companies pay Transgaming, but it would be really interesting to know. 

Also, there is actually something awesome coming to Wine in the near future, the ["Command stream"](http://www.winehq.org/pipermail/wine-devel/2013-September/101106.html).
It was something done by the team at [Codeweaver](https://www.codeweavers.com) (Makers of Parallel, a closed source fork of Wine), that multithread OpenGL call and allow games to run 100% faster than it was before. It's a big step forward, I tried it with Skyrim but with some other games too, performances are really fantastic with this beast turned on.

{<4>}![Skyrim poster](http://lifeasadigitalsalad.files.wordpress.com/2013/11/the_elder_scrolls_v_skyrim.jpg)

I made a custom engine with Wine latest version using a patch from the WIP brnch of the Command Stream. I installed Skyrim, and oh my god. I was able to play the game in high, with graphical mods, on my Macbook Pro Retina (NVIDIA 650M) at 40-50 FPS. 
It's like 95% of what the Windows version can do. 
I plan to do a post about that someday, and I'll post a link to the patched compiled engine.

There are also a translation layer released by Valve, which doesn't emulate the whole Windows API but just the Direct3D to OpenGL, it's called [ToGL](https://github.com/ValveSoftware/ToGL).
I'm really glad that Valve open sourced that, but I would suggest that every new game should be wrote using OpenGL... Or that you write an engine capable of targeting both Direct3D and OpenGL (and others). So you make call to your abstract rendering engine, and then you're rendering engine make call to OpenGl or Direct3D depending of the platform.

If you're on a Mac and you want to play Windows games or applications, you can start using [Wineskin](http://wineskin.urgesoftware.com). It's an GUI too for Wine which ease the Wine wrapper creation process by 1000%. 
Also, the Wine official applications/games [database](http://www.winehq.org) have a ton of ressources on what to install and how to make a specific game to run under Wine

### But why it's like that?

Apple played a big part on how the Mac games market is shaped. Apple is late, if you talk to any Mac graphics developer, he will tell you that Apple graphics driver are really late.
That's why even some native games are not as fast as there Windows counterpart even if they are native. 
Mac market share is also a lot thinner than the Windows one; which is why companies don't allow a very big budget to be spent on porting/releasing their games under OSX.

###In the end

I'm really looking forward about playing on Mac and Linux, in my opinion, every games should be wrote in a platform independent way, it's maybe harder to do, but in the end you don't ask yourself or making peoples sad because your games isn't available on X Platforms. Also the Mac market share is [growing fast](http://appleinsider.com/articles/14/01/09/apples-domestic-mac-sales-surge-285-as-overall-pc-market-shrinks-75), which mean more and more potential Mac players.
And you don't make yourself a fool by releasing a dirty port using Cider or Wine that run poorly on decent hardware. 
That argument is used a lot by the vocal gaming community, and it's now an accepted fact that games perform poorly on Mac. But they perform poorly not because it's a Mac, but because the technologies used to make the game offer a neat advantage on Windows.

I tinkered a lot with Wine, I played and play a lot of games that run under Wine, I can get really decent performance nowadays, but a true native game (I'm looking at you [Elder Scrolls Online](http://elderscrollsonline.com)) will outperform non native game by a lot.

There is a ton of things I didn't covered in this article, but I'm sure I'll have another opportunity to speak about it in a future article.

{<5>}![ESO](http://www.justpushstart.com/wp-content/uploads/2014/01/teso.jpg)


