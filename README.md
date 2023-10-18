# Make (iOS) BBC news great again

Recently, as many other people also noticed, older versions of the BBC news application (5.x and earlier) stopped working with an unsupported/expired error message, they could not be used at all. The solution was users were forced to update to version 7 of the application, which all I can summarise to is being a "piece of s...". No longer can you read news without signing in (wtf?), and these reviews from the app store sum up what people think of how the new app looks:

![Wonderful highly rated reviews of the new app version](/reviews.jpeg?raw=true)
![Yet more highly rated reviews of the new app version](/reviews2.jpeg?raw=true)

What's most infuriating about this is that unsupported/expired error message **is completely fake**, it's sole purpose is to force users to upgrade to a newer version of the application which includes more tracking and of course forcing you to have a useless/pointless bbc account - no not to help you, to track you. But, there is a solution... And it likely works on supposed old versions of iOS that the bbc wrongly claims are "not supported".

## Jailbroken device solution

1. Get filza from cydia
2. If you do not have an old version of the bbc news app, get something like appstore++, then downgrade in the app store to bbc news version 5.27.1 ideally
3. Open filza and navigate to (note: iOS 12+, for older devices this will be a different path): /var/containers/Bundle/Application/
4. Find the "BBC News" folder and open it then open BBCNews.app
5. Open Info.plist
6. Open Root and scroll down to CFBundleShortVersionString, change it to 99999.99999.99999.99999, save the file and close
7. (Optionally) change some of the other settings, there's typical bbc tracking trash in here like firebase, google adverts, facebook, etc. some with toggles
8. Open the old version of the app and marvel as it now functions fine

## Non-jailbroken device solution

Note: I have not done this, so I cannot document how to do it, but the rough steps are:

1. (Optionally) obtain an old version of the bbc news app, 5.27.1 is ideal. From where, somewhere on the internet, perhaps. This will be a .ipa file
2. Rename the .ipa to .zip, open it and extract the file BBCNews.app/Info.plist file
3. Edit this file with a plist editor, I have not tried this but it is the first one on github I found: https://github.com/corpnewt/ProperTree
4. Change Root -> CFBundleShortVersionString to 99999.99999.99999.99999
5. (Optionally) change some of the other settings, there's typical bbc tracking trash in here like firebase, google adverts, facebook, etc. some with toggles
6. Save the file, replace the BBCNews.app/Info.plist file in the .ipa
7. Sign the file, this typically was done using something like Cydia Impactor http://www.cydiaimpactor.com/
8. Load the file to your phone and run it, it should magically work just as it used to
