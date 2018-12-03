# Udacity AB Testing
This is the final project of the Udacity AB Testing class that I completed in early 2018. The goal is to conduct an AB test on a
hypothetical new feature for Udacity's webpage. Here's the project overview:

At the time of this experiment, Udacity courses currently have two options on the course overview page: "start free trial", and 
"access course materials". If the student clicks "start free trial", they will be asked to enter their credit card information, 
and then they will be enrolled in a free trial for the paid version of the course. After 14 days, they will automatically be charged 
unless they cancel first. If the student clicks "access course materials", they will be able to view the videos and take the quizzes 
for free, but they will not receive coaching support or a verified certificate, and they will not submit their final project for feedback.

In the experiment, Udacity tested a change where if the student clicked "start free trial", they were asked how much time they had 
available to devote to the course. If the student indicated 5 or more hours per week, they would be taken through the checkout process as 
usual. If they indicated fewer than 5 hours per week, a message would appear indicating that Udacity courses usually require a greater 
time commitment for successful completion, and suggesting that the student might like to access the course materials for free. At this 
point, the student would have the option to continue enrolling in the free trial, or access the course materials for free instead. This 
screenshot shows what the experiment looks like.

The hypothesis was that this might set clearer expectations for students upfront, thus reducing the number of frustrated students who 
left the free trial because they didn't have enough time—without significantly reducing the number of students to continue past the 
free trial and eventually complete the course. If this hypothesis held true, Udacity could improve the overall student experience and 
improve coaches' capacity to support students who are likely to complete the course.

The unit of diversion is a cookie, although if the student enrolls in the free trial, they are tracked by user-id from that point forward.

Here's the list of metrics Udacity's considering tracking: 
* Number of cookies: That is, number of unique cookies to view the course overview page. (dmin=3000)
* Number of user-ids: That is, number of users who enroll in the free trial. (dmin=50)
* Number of clicks: That is, number of unique cookies to click the "Start free trial" button (which happens before the free trial screener is trigger). (dmin=240)
* Click-through-probability: That is, number of unique cookies to click the "Start free trial" button divided by number of unique cookies to view the course overview page. (dmin=0.01)
* Gross conversion: That is, number of user-ids to complete checkout and enroll in the free trial divided by number of unique cookies to click the "Start free trial" button. (dmin= 0.01)
* Retention: That is, number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by number of user-ids to complete checkout. (dmin=0.01)
* Net conversion: That is, number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by the number of unique cookies to click the "Start free trial" button. (dmin= 0.0075)
