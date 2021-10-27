## Job description
Technical Test (Backend-side
automation)  
##### Part I (Essential)    
● Create a custom object “Weather Track”. Users should be able to access Weather
Tracks only if they have access to an associated Account record. The new object
should include fields necessary to track the weather conditions (please, choose field
types properly):

![image](https://user-images.githubusercontent.com/84872903/139049246-dfe43ad6-dfed-4cf7-83ac-8b7be5a56a95.png)

● Don’t forget about Tab and Page layouts for Weather Track object, and the related
list on an Account layout as well.  
● Whenever Billing City on an Account level is filled in or updated , the application
should automatically create a new Weather Track record with information about
weather conditions in an corresponding location.  
● You can use any free weather API you’d like, for example, this one:
https://openweathermap.org/. Please, properly store API tokens in Salesforce!  
● Good positive and negative Unit tests are highly recommended!  
● Possible exceptions should be handled properly (for example, when an external
Weather API service is not available for some reason).  
##### Part II (Optional)  
● Implement a nightly job to process all Accounts where:  
○ Billing City is NOT empty  
○ Without an associated Weather Track record with Date = TODAY. (We don’t
need to process such accounts because we’ve already received their weather
today).  
● The job should create Weather Track records for each Account.  
● Add Apex unit tests.  
Good luck!  
## Job performance
A custom "Weather Track" object was created.  The getWeatherWithSite class is used to create records in it. Tracks changes, in the "Billing City" field of the account, the changeAccountBillingCity trigger, it also reacts to the account creation and triggers the class for record creation.  
The nightlyJobCreateWeatherTrack class is used for the second part of the task. It checks accounts for which no record of the "Weather Track" object was created today and creates one for them. This class checks on schedule.
![Screenshot_1](https://user-images.githubusercontent.com/84872903/139051606-12f55790-a137-47c1-8458-9366c1c6439c.png)
