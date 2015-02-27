# TinderJavaAPI
An easy to use Java API for Tinder.
This is a hobby project that I created. 

Usage:

1. Run java -jar Tinder.jar FACEBOOK_ACCESS_TOKEN FACEBOOK_USER_NAME lat lng or add the jar file to your project and call the methods.

2. Enter your facebook access token and facebook user name.

3. To get the access token, the simplest way is to go to this [URL](https://www.facebook.com/dialog/oauth?client_id=464891386855067&redirect_uri=https://www.facebook.com/connect/login_success.html&scope=basic_info,email,public_profile,user_about_me,user_activities,user_birthday,user_education_history,user_friends,user_interests,user_likes,user_location,user_photos,user_relationship_details&response_type=token), log in and then copy the auth token out of the URL before you are redirected to.

4. To get the facebook user name, click on your profile right next to the home page and copy the part after https://www.facebook.com/ . For example myt url is https://www.facebook.com/asim.sinan and I need to copy asim.sinan

5. Then do whatever you want (Dont change your location so quick!!!!).

6. Feel free to create your own refactored api.

7. Watch it in action [TinderJavAPI](https://www.youtube.com/watch?v=Iy6QRbOaDKA&list=UUIzA1E4_dZojyOzzjT2LhSQ).

<table>
  <thead>
    <tr>
      <th>Method name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>public void updateProfile(int distance, int gender, int ageMin, int ageMax, int genderFilter, String bio,boolean discoverable)</td>
      <td>Updates user's profile. distance:2-160, gender:0,1(0:male,1:female), age:19-55,genderFilter:-1,0,1(-1 male&female,0:male,1:female, bio:String, discoverable:true,false </td>
    </tr>
    <tr>
      <td>void updateLocation(double lat, double lng)</td>
      <td>Updates user's location according to lat,long values. Don't change it quickly.</td>
    </tr>
    <tr>
    	<td>void login()</td>
    	<td>Login to Tinder.</td>
    </tr>
    <tr>
    	<td>JsonObject getRecommendedUsers()</td>
    	<td>Returns recommended users as JsonObject. </td>
    </tr>
    <tr>
    	<td>boolean likeUser(String tinderID)</td>
    	<td>like a user given a tinderID. Returns match result as true or false. </td>
    </tr>
    <tr>
    	<td>TinderUser getUserProfile(String tinderID)</td>
    	<td>Returns a TinderUser object from a tinderID. </td>
    </tr>
     <tr>
    	<td>void begenmeninBokunuCikar()</td>
    	<td>Like them all!. </td>
    </tr>
         <tr>
    	<td>void listRecommendedUsers()</td>
    	<td>likes all the recommended users and prints them.</td>
    </tr>
         <tr>
    	<td>void addRecommendedUsersToMyList(JsonObject jsonResult)</td>
    	<td>Parses the json response, gets each recommended user and adds to the list.</td>
    </tr>
         <tr>
    	<td>public TinderAPI(String facebookToken, String facebookUserName)</td>
    	<td>Constructor for Tinder API. You must provide your facebook token and facebook user name.</td>
    </tr>
      <tr>
    	<td>TinderUser</td>
    	<td>This is the class that holds all the information related to the user. </td>
    </tr>
  </tbody>
</table>

### Sample Usage
```
TinderAPI tinder = new TinderAPI(args[0], args[1]);
tinder.login();
tinder.updateProfile(99, 0, 19, 55, 1, "Hi!",true);
tinder.updateLocation(Double.parseDouble(args[2]), Double.parseDouble(args[3]));
```
