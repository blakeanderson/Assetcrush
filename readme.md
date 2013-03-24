Instead of forking Peter Boctor's entire idev-recipes project and fixing the [appcrush][] utility, I made my changes and started a new repo. All credit should go to Peter. (I should note that Peter hasn't accepted any pull requests for quite some time even though the current script is broken, which added to the decision to make my own repo)

To recreate features of existing apps, we can use a big clue: the
images an app uses. This will often give us insight into how the
feature was built.

You can right click on an App in iTunes and see the app’s .ipa
file.

![image][]

An .ipa file is just a zip file that is easily expanded resulting
in a Payload folder that has the actual .app.

I edited Peter's [appcrush][] script, and changed the name to assetcrush, that automates the process of unzipping the .ipa and moves all the images to a folder on your desktop.

Point assetcrush at an .ipa file from the iTunes AppStore and it:

-   expands the zip file
-   finds all the images
-   puts them into a folder on your desktop

    `assetcrush '/Users/blake/Music/iTunes/Mobile Applications/iBooks.ipa'`

Peter's origin blog post:
[http://idevrecipes.com/2010/12/06/extracting-images-from-apps-in-the-appstore][]

  [http://idevrecipes.com/2010/12/06/extracting-images-from-apps-in-the-appstore]: http://idevrecipes.com/2010/12/06/extracting-images-from-apps-in-the-appstore
  [image]: http://idevrecipes.files.wordpress.com/2010/12/ibooksfinder.png?w=239&h=119 "Find iBooks app in iTunes"
  [1]: http://idevrecipes.files.wordpress.com/2010/12/ibookspayload.png?w=272&h=250 "iBooks Payload"
  [2]: http://idevrecipes.files.wordpress.com/2010/12/ibooksimages.png?w=300&h=220 "iBooks Optimized Images"
  [pngcrush]: http://pmt.sourceforge.net/pngcrush/index.html
  [Apple added the ‘revert-iphone-optimizations’ option to undo this optimization]: http://developer.apple.com/library/ios/#qa/qa2010/qa1681.html
  [appcrush]: https://github.com/boctor/idev-recipes/tree/master/Utilities/appcrush