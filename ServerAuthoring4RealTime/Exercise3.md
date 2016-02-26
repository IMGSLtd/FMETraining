<!--Instructor Notes-->

<!--Exercise Section-->
<!--NB: In GitBook world we don't give a number to exercises-->

<table style="border-spacing: 0px;border-collapse: collapse;font-family:serif">
<tr>
<td width=25% style="vertical-align:middle;background-color:darkorange;border: 2px solid darkorange">
<i class="fa fa-cogs fa-lg fa-pull-left fa-fw" style="color:white;padding-right: 12px;vertical-align:text-top"></i>
<span style="color:white;font-size:x-large;font-weight: bold">Exercise 3</span>
</td>
<td style="border: 2px solid darkorange;background-color:darkorange;color:white">
<span style="color:white;font-size:x-large;font-weight: bold">Orthophoto Notification System</span>
</td>
</tr>

<tr>
<td style="border: 1px solid darkorange; font-weight: bold">Data</td>
<td style="border: 1px solid darkorange">Orthophoto images (GeoTIFF)</td>
</tr>

<tr>
<td style="border: 1px solid darkorange; font-weight: bold">Overall Goal</td>
<td style="border: 1px solid darkorange">Provide email-driven access to orthophoto files</td>
</tr>

<tr>
<td style="border: 1px solid darkorange; font-weight: bold">Demonstrates</td>
<td style="border: 1px solid darkorange">Running a workspace in response to a notification</td>
</tr>

<tr>
<td style="border: 1px solid darkorange; font-weight: bold">Start Workspace</td>
<td style="border: 1px solid darkorange">None</td>
</tr>

<tr>
<td style="border: 1px solid darkorange; font-weight: bold">End Workspace</td>
<td style="border: 1px solid darkorange">C:\FMEData2016\Workspaces\ServerAuthoring\Notifications-Ex3-Complete.fmw</td>
</tr>

</table>

---

As a technical analyst in the GIS department a recent project involved setting up a Data Download solution for users to serve orthophoto data to themselves. Having read up about notifications in FME Server, you think that it should also be possible to set up a system that uses email-based automation.

So far you have set up a system for incoming email notifications to be registered by FME Server. Now you must create a workspace to process these and publish it to FME Server. The workspace must then be triggered by a notification topic.

---

<!--Person X Says Section-->

<table style="border-spacing: 0px">
<tr>
<td style="vertical-align:middle;background-color:darkorange;border: 2px solid darkorange">
<i class="fa fa-quote-left fa-lg fa-pull-left fa-fw" style="color:white;padding-right: 12px;vertical-align:text-top"></i>
<span style="color:white;font-size:x-large;font-weight: bold;font-family:serif">Miss Vector says...</span>
</td>
</tr>

<tr>
<td style="border: 1px solid darkorange">
<span style="font-family:serif; font-style:italic; font-size:larger">
This exercise continues where exercise 2 left off. You must have completed exercise 2 to carry out this exercise.
</td>
</tr>
</table>

---

<br>**1) Create Workspace**
<br>Start FME Workbench and begin with an empty workspace. Simply add a Creator and Logger transformer:

![](./Images/Img4.39.Ex2.InitialWorkspace.png)

This will give us a workspace to run in response to an email; albeit one that doesn’t do much yet. We're just creating this to check that we can get the setup to work.


<br>**2) Save and Publish Workspace**
<br>Save the workspace and publish it to FME Server. We only need it to be run (not do anything special) so register it only with the Job Submitter service.


<br>**3) Create Subscription**
<br>Return to the FME Server web interface and navigate to the Notifications page. Click on the Subscriptions tab and click New to create a new Subscription.

Call the subscription "Process Images Request".  Subscribe to the topic ImagesIncomingRequest:

![](./Images/Img4.40.Ex2.CreateSubscription1.png)

Now set the protocol to Workspace and select the workspace uploaded in the previous step:

![](./Images/Img4.41.Ex2.CreateSubscription2.png)

Click OK to create the subscription. This will cause the workspace to run every time an incoming email triggers the ImagesIncomingRequest topic.


<br>**4) Test Subscription**
<br>Test the subscription by sending an email to the existing publication's email address.

This time, instead of monitoring the topic (although it will appear there again), check the Jobs page. You should see that the workspace has been run in response to the email:

![](./Images/Img4.42.Ex2.JobLogShowingTriggeredWorkspace.png)

This proves that the workspace has run.


---

<!--Person X Says Section-->

<table style="border-spacing: 0px">
<tr>
<td style="vertical-align:middle;background-color:darkorange;border: 2px solid darkorange">
<i class="fa fa-quote-left fa-lg fa-pull-left fa-fw" style="color:white;padding-right: 12px;vertical-align:text-top"></i>
<span style="color:white;font-size:x-large;font-weight: bold;font-family:serif">Ms Analyst says...</span>
</td>
</tr>

<tr>
<td style="border: 1px solid darkorange">
<span style="font-family:serif; font-style:italic; font-size:larger">
Again, in a training course more than one student might be using the IMAP account fmeimageprocessing@gmail.com, so don't be surprised by multiple job results! Also, if you're using your own personal email account, any email you receive is going to trigger the workspace, so you too should not be surprised by multiple job results.
</span>
</td>
</tr>
</table>

---

<!--Exercise Congratulations Section--> 

<table style="border-spacing: 0px">
<tr>
<td style="vertical-align:middle;background-color:darkorange;border: 2px solid darkorange">
<i class="fa fa-thumbs-o-up fa-lg fa-pull-left fa-fw" style="color:white;padding-right: 12px;vertical-align:text-top"></i>
<span style="color:white;font-size:x-large;font-weight: bold;font-family:serif">CONGRATULATIONS</span>
</td>
</tr>

<tr>
<td style="border: 1px solid darkorange">
<span style="font-family:serif; font-style:italic; font-size:larger">
By completing this exercise you have learned how to:
<br>
<ul><li>Create a new Subscription</li>
<li>Use the Workspace subscription to run a workspace in response to a topic</li>
<li>Check the job history to prove a workspace was triggered correctly</li></ul>
</span>
</td>
</tr>
</table>   
