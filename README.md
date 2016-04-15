# frenchgirls-challenge
>Take some time to figure out all of the different tasks that need to be done to complete this app. 
>Write them down as if you were planning this project yourself. These may take the form of user stories, checklists, an outline of features,
>whatever makes the most sense to you. 
>This step doesn't need to be very technical, it just needs to identify all the unique chunks of work that 
>you think would be required to complete this app. However you decide to tackle it, document your work in your github repo.

###this is my answer.
####1. user stories
A user enters the first screen. We bring up a conversion between Scotch and this user. In this screen, we are telling why and what will be the user's task. After this boarding screen finishes, we present this user three costumes to choose from. Once this user picks one, we will dress 
Scotch based on this user's choice. 

####2. checklists
0. two screens. first: boarding screen, second: costume-picking-and-dressing-up
1. image assets in first screen
2. conversion content in first screen
3. background color and text color used in the first screen, such as in the bottom button.
4. image assets in second screen
5. text color, font, font size, background color in the top text label after the user choosed a costume. 
6. endpoint of more costumes

####need some clarification such as 
0. the launch screen has an animiation to zoom to user. It needs to be a different screen to have this feature. It will make this app 3 screens.
1. full screen for all screens? 
2. 1 min. to have 2 more costume? will be it too long?
3. support all iOS devices size and orientation? 

####3. outline of features
0. support all iOS devices size and orientation? 
1. launch screen and lanch screen zoom-out anmiation
2. boarding screen with predefined images and text in the top and bottom
3. the text in the top will be changed once the user's tap the buttom button
4. boarding screen will be dismissed once the user taps the butotn with the ending text.
5. 2nd screen shows up with predefined image of Scotch and 3 costumes 
6. 3 costumes is formed as a circle with equal distance. 
7. once a user flint the costume circle, the circle rotates based on the flint direction
8  once this user selects one costume, we will dress Scotch with the set of costume and zoom out Scotch. all other costumes will be falling down 
to the floor with bouncing animation.
9. this user can tap Scotch. we will take off the selected costume from Scotch, form the circle of costume with 5 costumes. 

>Next, take some time to get more technical. Plan out what the major technical components are, 
>and define how they work together. This is your chance to be an architect and make high-level decisions about what 
>technology you want to use, and how you want to implement it. 
>Write this technical strategy down in a way that you feel would be useful if you were to actually code this project.

##this is my second answer
1. Technically, this is a simple task. To architecture these two screens(or three, I would say 3 screens with the animated launch screen).
Two view controllers  - the animated launch screen can be just a view in the first view controller
2. Models - there is no need to have a model for the first screen. for the second screen, I will define a Costume model object. It will have some 
properites just like what an dictionary in the plist (or the json data) has. I will also add one more boolean properity: selected, and one more NSString to represent
its location on the device (basically, we cached this image after we fetched from remote server).
3. Views - the views in the first screen are straightforward, one UILabel for the top text. one UIImageView for the Scotch and one buttom UIButton 
for user's interaction.
the views in the second screens will be a little bit complicated, it includes an UIImageView in center, 3 default costumes UIimageViews (plus two mores in a short min.)
the most complicated part in this screen will be the differnt animation, but its definitely doable.UIKit Dynamics, Facebook Pop etc can be solutions.
There will be a little network request needed to download more costumes. It can totally be done with NSURLSession API. We can actually start this 
API request once the 2nd screen is showing while there is no local cached. Otherwise, we will just the local cached one. No matter we want to just cache
this image, or with all other json contents, we can write to a text file or plist file for the two extra costumes. The images will be files on the disk.

Since the task is only about these two screens, I estimate it's an assignment between 2-5 hours. The first screen (including the zooming-out 
lanch screen) will cost about 30-45 mins. The 2nd screen will be definitely tricky. One of my concerns is that the absolute coordinate of costome
with Scotch. It might not be easily fit between costumes and scotch when phone size changes. 
