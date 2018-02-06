# Project 1: Word Magnets

Goal: To build a Magnetic Poetry App.

## Requirements ##

1. Each partner individually completes the Dr Magneto Exercise and posts it to mycourses (due Monday 2/5)
2. Get a partner and submit your names to the instructor. (due start of class, Thursday 2/8)
3. Your Xcode project must compile without errors to get credit for each checkout, otherwise you will receive a 0 for the checkpoint.
	1. Double check your .zip submissions to make sure no files are missing in Xcode (Hint: use a separate machine to verify)
5. All work must be posted on a Github
	1. Regular commits with descriptive comments (-2% if not done)
	2. Post names on all source files (-2% if not done)
	3. Create a README.md with images describing the app for each checkpoint (-2% if not done)
	4. Add comments for any code samples you found online (-2% if not done, copying another student's work result in an F for the course)

### Required App Features for Checkpoint #1 (due Monday night 2/12):

1. This is worth 10% of Project 1 grade
2. For this first deliverable, make sure that both partners do (or attempt) ALL of the coding requirements.
3. The app is universal and runs on both iPhone and iPad. (-2% if not done)
4. The app uses Xcode 9.2/Swift 4/iOS 10.3+ (-2% if not done)
5. The app will start up with a set of related words on the screen - see MyCourses for word sets, or come up with your own. (-2% if not done)
6. The words are draggable. (-2% if not done)
7. At startup, the word magnets will be neatly grouped near the top of the screen. 
	8. Write code that places the magnets in rows, and puts space between words and the rows. 
	9. To do this you will need to access the width and height of the magnets (labels) so that you know how tall to make your rows, and when you've run out of room on a row. All word labels will have exactly the same height which is label.frame.size.height, and differing widths which is label.frame.size.width (-3% if not done) 
	10. Tip: This might be a little tricky for you. Both partners should first attempt to do this by themselves. Ideally if you both get it working, you can submit the "best" solution.
8. The Dr Magneto word magnets are too small, especially the ones with a single character. Make them bigger (-3% if not done)
	9. Apple recommends a minimum touch target size of 40x40 points.
	9. Solution A: Add a space to both of the ends of each label's text, then center align the text in the label. 
	10. Solution B: Adjust the label inset
	11. Solution C: Use attributed text (more options to control spacing)
9. The app has a custom App icon - designed and created by you - for all iPad and iPhone sizes. [Here is a tutorial on how to create an app icon.](https://designmodo.com/ios-app-icon-photoshop/)If you already have an image file you think could work as your icon (at least 1024x1024 pixels ideally), services like <http://appicon.build> will generate all of the required icon sizes for you.(-3% if not done)
10. Create a start up screen (on LaunchScreen.storyboard) that has the name of your app and your team members on it. Use an image (drag out a UIImageView), use auto-resizing or auto-layout to position it, and make sure it looks good on both iPhone and iPad. (-3% if not done)
11. BOTH partners bring the app to class installed on their iOS hardware (-3% if not done)

### Required App Features for Checkpoint #2 (due Monday night 2/19) - This is worth 10% of Project 1 grade

1. The user can load at least 3 distinct sets of words. (see the Tables I-III Walkthrough for ideas on how to let the user choose something from a list). Because multiple view controllers will depend on the same data, ideally you have that data stored in just one place. Also, use some emojis if you like - <http://getemoji.com> & <http://emojipedia.org> - (-6 if not done)
2. Before loading a new word set the app needs to get rid of all of the old UILabels. [See this Stack Overflow post on how to do this.](http://stackoverflow.com/questions/24312760/swift-how-will-i-remove-all-the-subviews-of-a-view/28516228#28516228) (-3 if not done)
3. When new word sets are loaded, make sure that the words are not too close to the top or edges of the screen for the user to tap. Test for this fact on a real device. (-2 if not done)
4. Hide the status bar - you can do this on the General settings page for the Xcode project (-2 if not done)
5. Make sure your Springboard app name matches the name on the icon - [see developer.apple.com - Updating the Display Name of Your App](https://developer.apple.com/library/content/qa/qa1823/_index.html) (-2 if not done)
6. Get rid of all compiler warnings - including those for unused variables, missing icons, and broken Storyboard constraints (-1 per compiler warning)
7. Make sure you still meet all of the checkpoint #1 requirements (-1 per requirement not met)


### Required Final App Features (Due Sunday Night 2/26) - No Late Submissions Will Be Accepted - Bring to Class on Your Device the Next Day: ###

1. The app should by now been thoroughly tested on iOS hardware:
	1.The app should display properly on either landscape or portrait orientation, and on both iPhone and iPad. I recommend choosing one orientation for the app, either portrait or landscape, and making that the sole orientation of the app.
	2. There should be no obvious usability issues.
3. State Preservation. The user's current chosen category will be stored in UserDefaults, and the chosen word set will be displayed in when they launch the app.
4. Use a larger font size when creating word magnets for an iPad. You can either: look at the width of the screen (do a google search on how to get the width of the screen) and base the font size on that value, or check to see the device's "user interface idiom" - [see this Stack Overflow post:](http://stackoverflow.com/questions/24059327/detect-current-device-with-ui-user-interface-idiom-in-swift) Be sure that the words can still fit on the smallest iPhone screens (the iPhone 5/iPhone SE)
5. The user can share their poetry (a screenshot of the entire poem) with others using Social Networks with the `UIActivityViewController` class.
6. The user can choose a poetry background image from their Photo Library with the `UIImagePickerController` class.
7. The app meets all requirements of checkpoints #1 and #2 (-5% per requirement not met)
8. Because multiple view controllers will depend on the same data, you should have a model class that manages/contains your application data.
	9. Use dependency injection and do not make this a strict singleton

9. Code Conventions: see the [Swift Style Guide](https://github.com/SuperEasyApps/swift-style-guide)
	1. Class names are capitalized, instance variables begin in lowercase (-1 per incidence)
	2. Code files in the Xcode Project Navigator are organized in groups for example, VC, Model, Lib, Helpers, Extensions etc...(-5 if not done)
	3. Get rid of all compiler warnings - including those for unused variables, missing icons, and broken Storyboard constraints (-1 per compiler warning)
	4. Use Extensions to implement and organize your delegate methods
	5. Organize your code with order ivars, outlets, init, deinit, actions, and functions
	6. Use a Constants struct to organize all magic numbers and strings
	6. //MARK: - Some Category - in your view controller classes to organize your code. Possible categories include ivars, Private Helper Methods, Storyboard Action Methods, Initialization, View Lifecycle, GestureRecognizer Action Methods, UIImagePickerController Delegate Methods, and so on.
	
10. If the app crashes, there will be an additional penalty of -10%

### Extra Features: ##

Doing all of the above gets an 85% - to get a higher grade you need to go "above and beyond". 

**NOTE**: Be sure to document your extras in a separate file or in the comments field of the dropbox. If you don't, you will not get credit for them. Here are some ideas:

1. Add Word to existing word set/Make new word set
2. Subclass UILabel and override the `drawText(in rect: CGRect)` and  `textRect(forBounds bounds: CGRect, limitedToNumberOfLines numberOfLines: Int)` 
3. Delete Words, and animate it - look at Hello RIT-2
4. Rotate words - see GestureRecognizer Demo in mycourses
5. Custom Fonts - use a UIPickerView - see this tutorial - <http://codewithchris.com/uipickerview-example>
6. Slider for Font Size - use a UISlider see this tutorial - <http://sourcefreeze.com/ios-slider-uislider-example-using-swift>
7. UI Animation - go back and look at Hello RIT-2
8. If the app force-quits, the user's last poem should be preserved, the previous background image will be restored, and all of the word magnets should be in the same location.
... you decide!!! ...

### Handy Links

* Some examples of previous Magnet projects and best practices are here: [Project-1-comments.pdf](http://igm.rit.edu/~acjvks/courses/2017-spring/340/pages/p1-images/Project-1-comments.pdf)
* <http://magneticpoetry.com>
* [Lovecraftian Letters](http://forum.rpg.net/showthread.php?590734-Lovecraftian-Letters-HPL-Fridge-Magnet-Set-Preorder-Special)
* <http://getemoji.com>
* <http://emojipedia.org>
* [nshipster.com - UIActivityViewController](http://nshipster.com/uiactivityviewcontroller/)
* [developer.apple.com - UIActivityViewController](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIActivityViewController_Class/index.html)
* [developer.apple.com - UIActivity](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIActivity_Class/index.html)
