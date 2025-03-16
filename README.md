# Forest Angel 🌳🌲🌱
## Introduction 
This is an app dedicated to protecting the environment through a unique and innovative approach! Deforestation is occurring at an alarming rate, and illegal tree cutting continues to threaten our forests. 

This app aims to track every tree that is cut or planted hence providing a clear and accurate measure of tree cover changes over time. 

## Description of the App 📱
The app uses firebase to store data at backend.

-	App begins with a 3 page intro slider.
-	Next screen takes the user to simple login asking for name (not stored online, just for Hello!), and selecting Home state and district.
-	Main home screen has 3 bottom navigations and a “Upload” Floating action button

### Home Fragment 📱
-   Greets user by “Hello {Name}”, on top
-   Contains 4 buttons
-   Report Planted Trees (for Home district)
-   Report Cut Trees (for Home district)
-   View All Data
-   View Your State Data
-   Also shows the summary of data uploaded by user.
    
### Track Fragment (for viewing data of a specific state) 📱
-	Shows list of all states
 
### Dashboard Fragment 📱
-	Shows Name, Home State and District
-	All Data Uploaded By User Button -> Takes to another screen and shows all data uploaded by user
-	Help Button -> Shows some help content
-	About Button -> Shows some about
-	Feedback / Suggest a Feature Button -> Gets some feedback from the user

### Upload Floating Action Button 📱
- Activity 1: Get State and District from user.
- Activity 2: Buttons to report planted or cut trees. Also shows current data for the selected district. 
- Activity 3: Differs based on whether user selects to report planted or cut trees. Shows a number selector to pick a number. Then a Button to ‘Validate and Register’
- Activity 4: To check false data reports, user has to validate by uploading an on-site image
  -	Add an image proof 🖼️
      -	User has to upload an image, that will be stored on firebase. ML has been implemented to check      false fake images
  

#### After validation, data is successfully uploaded. ⬆️

## Firebase Data Structure: 
~~~
forest-tracker
|    -Feedback
|	-Random UUID: “{Feedback}”
|
|
|    -Feature
|	-Random UUID: “{Suggested Feature}”
|
|
|    -Trees
|	-Locations
|	    -State 1
|		-District 1
|		...	
|		...
|	    -State 2
|		-District 2
|		...
|		...
|	    ...
|	    ...
|
~~~     

### Explanation
##### Database for locations has been maintained as shown above.
-	When someone uses Image Proof as validation, the image is uploaded to Firebase Storage under  \images\ by the name
    -	**{State}\_{District}\_’n’ Trees Planted_DD-MM-YYYY_HH-MM-SS_AA**
    -	**{State}\_{District}\_’n’ Trees Cut_DD-MM-YYYY_HH-MM-SS_AA**
-	When someone suggests a feature, it is stored under “Feature” under a random UUID as 
    -	**{UUID}: “Suggested Feature”**
-	When someone writes a feedback, it is stored under “Feedback” under a random UUID as 
    -	**{UUID}: “Feedback”**

## Privacy 🔒
- User’s privacy has been taken very seriously. You can see, instead of maintaining such a large database, location could be fetched easily using GPS, but it has not been done. 
- Similarly, the name is not uploaded anywhere. It is stored only in the phone only for greeting purposes. Same is the case with the Home state and district data.

## Future Developments
1.	Add more validation options and optimize the existing ones. Like, someone can still enter false Tree ID or upload any image, there is no method to check that even. Math problem is also not apt here.
2.	Make the App’s UI and UX more interesting.
3.	Add some incentives. For instance, TreeCoins. A user would get, say, 10 TreeCoins for every tree cut/planted report. That would make it even more interesting. 
Also, can maintain a leaderboard and give some rewards, it would make people more willing to participate.

## Contribution 
Any contribution on this project will be much appreciated.

### Thank You 
