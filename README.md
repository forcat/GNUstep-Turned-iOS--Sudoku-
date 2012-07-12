#GNUStep turned iOS. (Sudoku)

###The Aim
The aim is to produce an iPhone App. This iPhone app to be precise:

Features should include:
- Local file saving (Originally Implemented)
- Downloadable puzzles from the internet
- Nice User Interface
- Multiple difficulties (Originally Implemented)

File saving and multiple difficulties is implemented through the original codebase I forked. Naturally this code will require substantial modification for use on an iPhone!

![Mock-Up Image](http://s12.postimage.org/jmxb17smz/untitled.png)

In the mockup you can see the difficulty buttons, a basic grid to demonstrate where exactly the Sudoku game will be and a basic taskbar. (The taskbar will have 4 options - "New", "Open", "Save" and "Download").

###How?
By building upon the good work on the Sudoku logic from the original repo - the task becomes a simple case of:
1 - Code Review
2 - Removing and Re-implementing
3 - UI Design
4 - Conversion
5 - Testing

**1 - Code Review** - Due to the simplicity of the codebase I'm starting with, this is mainly just going over the code and getting accustomed to it and understanding how and what it actually does.

**2 - Removing and Re-implementing** - Parts of the code are no longer required - UI specific parts in particular. (PuzzleBoard class for instance) Furthermore, some of the filesaving code could be rewritten to make it more suitable for working with the native SQLlite implementation on iOS. Ultimately _"If it aint broke, dont fix it!"_ applies here though!

**3 - UI Design** - Surprisingly this actually appears to be one of the more complex tasks! Due to the UI classes available on the iOS SDK there is actually no native way of drawing a grid thats appropriate for this task. The current idea is to use the [moriarty library](http://bynomial.com/moriarty/) for this; and having an NSArray of UIButtons. 

**4 - Conversion** - Converting the old codebase to use the new UI leads to issues such as controlling so many buttons, keeping an internal representation of the data in the view is also a problem that shall have to be confronted.

**5 - Testing** - Finally, like any app - this will have to be debugged.

###Frequently Asked Questions

**So, you forked a repo of a GNUStep Example.. Why?**
Actually, [the repo I forked](https://github.com/michaelwisely/GNUstep-Sudoku/) consisted of some very good code, it contained a lot of the logic required for a Sudoku application and also implemented a very interesting file format for storing game state.

The other *really cool* aspect of this is that I can work on the Objective-C code in a Windows or Linux environment to get the back-end logic perfect before finalising UI things in XCode - very neat for working on the go!

**The plan is to convert this to run on an iPhone, right?**
Yes.. ermm... in a roundabout way. Before this happens I need (or want too anyway) make a few additions and modifications to the code. 

**The original repo was GPL right; what's the deal with licensing of this code?**
Obviously the same licensing applies, do as you please and share the love.

**Even if it goes on the App Store?**
Yes! Despite the obligations to GPL the code due to the codebase I've inherited from, I would do it anyway! Realistically, if I didn't want to GPL the code I could just re-implement all the features myself; however there seems to be a bit of a lack of _complete native (Objective-C/iOS SDK) example applications_. So you can add one to the list!

###Progress Log

**12/07/2012 -** First Commit, woo! Essentially rewrote some of the UI handling code in the back-end. It was good code, but I don't really like code duplication - so I rewrote the functions that handle setting the difficulty of the game; and merged them in to 1 function.

It may not be as fast, but for a non-intensive task I think code readability comes first! To further ensure code readability (and style) - all loops now use '_i+=1_' for incrementing; as there was a mixture of that and '_i++_' being used. 

**I must say though - the code I've forked was of a really good quality, and these tweaks are mainly personal preference!** 