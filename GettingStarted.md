# Installation

Swift is typically installed by downloading the appropriate programming environment; you don't need to download Swift seperately from an IDE. If you would like to use a version of Swift that is in the works (and that possibly has some bugs), you will need to download it from the [Swift.org download page] (https://swift.org/download/#latest-development-snapshots).

You may notice that Swift.org only gives instructions for downloading to OS X and Linux. Apple does not have IDEs for any other operating systems, so if you do not have a Mac or Linux machine, you may not be able to code in Swift.

**On a related note, I am using a Mac and therefore will be using Xcode for all my Swift needs.** While I do point out some alternatives to writing with Swift on Mac below, after this section, I will write only from the point of view of an Xcode user.

## Installing on an OS X Machine

The IDE for Swift on a Mac is Xcode. To download Xcode, simply open the App Store on your Mac, search for Xcode, and download it for free.

Note that Swift.org features instructions for [getting Swift on Apple platforms] (https://swift.org/download/#apple-platforms), but that these instructions **only apply to those who want to try a version of Swift that is not officially released.** If you want to use the most current version of Swift backed by Apple, just download Xcode as I've described above.

## Installing on a Linux Machine

Apple gives instructions for using Swift on Linux here: https://swift.org/download/#linux

And you can also read this introduction to using Swift on Linux here: http://www.raywenderlich.com/122189/introduction-to-open-source-swift-on-linux

## Installing on a non-OS X, non-Linux Machine
As I use a Mac, I cannot personally try any of the following work-arounds for non-OS X users, but it may be worth looking into further if you really want to code with Swift. **I cannot vouch for their validity. They merely came from a quick Google search to provide a starting point for someone looking for alternative methods to using Swift. Do more research before attempting any of them!**:

- For programmers on Windows machines, check out [Silver] (http://elementscompiler.com/elements/silver/), a Swift IDE.

- You can also look into using a virtual machine. While I think it's against Apple licensing terms to run OS X on non-Apple hardware, you could try Linux. [VirtualBox] (https://www.virtualbox.org/) is popular and open-source.

- For programmers who do not want to/cannot install anything at all, try [RunSwift] (http://www.runswiftlang.com/), a website which allows you to use Swift in the browser. This requires an internet connection and seems only to support Swift 1.2, not the most up-to-date version, Swift 2.

# Using Xcode

## Playground or Project?

Xcode has a feature called [Playground] (https://developer.apple.com/library/ios/recipes/Playground_Help/Chapters/AboutPlaygrounds.html) where you write code and see results immediately on a side panel. It reminds me of the Python shell because it displays your work immediately and you can use it to test bits of code before saving to a file and running it. A [Project] (https://developer.apple.com/library/ios/featuredarticles/XcodeConcepts/Concept-Projects.html), on the other hand, is just what it sounds like--it gets you started with a set of all the files that you'll need to compile and run to see the effects of what you've written.

**To use Playground:** Open Xcode, select File > New > Playground. You are prompted to name your .playground file, so you can save your work. When Playground opens, the default code is:

```swift
//: Playground - noun: a place where people can play

import UIKit

var str = "Hello, playground"
```

You can see that it imports UIKit for you, which is a framework that allows you to build a user interface and use event handlers. You don't need it simply to print "Hello, world," in Playground, but you can read more about it here: https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIKit_Framework/

**To start a project:** Open Xcode, select File > New > New Project. You then choose among various templates based on the application you want to build; single view application provides enough code to simulate an app without too much unnecessary code. You'll be prompted to name your project, and on that same pop-up window, you can choose the language and device you're writing for. Make sure the language is Swift.

When your project template opens, you will see many folders and files on the left side of the window. The important stuff is in the very first folder. The first file in that folder is called "AppDelegate.swift." Open that and notice that, again, Xcode gives you a lot of code to start with. It gives you the UIKit to control your interface, @UIApplicationMain, and a class. This file holds your app behaviors for when it opens, closes, etc... Each function in this file has Xcode-provided comments explaining what they do.

## Hello, World!

In the top right hand corner of the Xcode window, you see three buttons that control which panels you see. Click them to open or close the panels. The only one you really need to write to the console is the "Debug area," which will appear on the bottom of the screen. If you are doing this in a project, make sure you also have the left panel open, the Navigator.

"Hello, world" in Swift looks like this:

```swift
// comments are preceded by two forward slashes
/* or you can write a multi-line comment
   with a forward slash followed by an asterisk
   and close it with an asterisk followed by a forward slash */

print("Hello, world")
```

You can type the print statement into Playground and see the result on the sidebar. There is really no boilerplate when using Playground. If your Debug area is open, the program will run automatically (if not, simply press the little triangle button at the top of the console/debug area to run it) and you should see the string printed in the console.

Or, you can write it as a project. There is lots of boiler plate when writing an app, but that's all given to you in the templates in Xcode; most of it seems to be app behaviors. If you selected a single view application, go into the AppDelegate.swift file as instructed above, and find the first function--it's called "application." Inside application, just write the print statement. Press command-s on your keyboard to save your change and press the play button in the top left corner of the Xcode window. Give it about 15 seconds; the simmulator will open a blank app and then the console in the Xcode window will show "Hello, world." You can quit the simulator to stop running the app.

# Sources

Elements http://www.elementscompiler.com/elements/silver/ Accessed Jan. 30, 2016.

iOS Developer Library https://developer.apple.com/library/ios/ Accessed Jan. 31, 2016.

RunSwift http://www.runswiftlang.com/ Accessed Jan. 30, 2016.

Swift.org https://swift.org/ Accessed Jan. 30, 2016.
