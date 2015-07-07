Title:Android HandlerThread
Date:2015-07-07 17:23
Category:Android
Tags:android,HandlerThread

####介绍
 android设计了Handler机制来实现线程间的通讯，在应用程序中为了实现同时完成多个任务，便可以创建多线程，而各个线程之间的通讯便是交由handler来实现。本文是建立在读者对android的handler机制有一定了解的基础上，并知道looper这个关键。

 Android对HandlerThread的描述：
 >Handy class for starting a new thread that has a looper. the looper can then be used to create handler classes. Note that start() must still be called.

Markdown 语法说明
android HandlerThread的使用及其demo leo chin
