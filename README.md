# College Scheduler App

This app contains features for college students to manage their classes, assignments, exams, and other miscellaneous to-dos. Here is a description of what it can do.

## Display
The app provides interactive, card-based displays of courses, exams, assignments, and to-dos. It displays all relevant info such as:
- Courses: title, course code, section, instructor, location, room number, time, days of the week, etc.
- Assignments: title, associated course, due date and time, complete/incomplete
- Exams: title, associates course, date, time, location, complete/incomplete
- To-do: title, associated course (if any), due date and time, complete/incomplete

The displays also allow the user to sort by due date, course, or complete/incomplete. To achieve this, the base functionality of all objects (courses, exams, assignments, to-dos) is captured in a base ActionItem class. The app maintains an ArrayList of all ActionItem objects, and we can filter the relevant items and then use comparators to sort the data by various criteria.

To create unique CardViews for each of our Items, we first made sure to initialize a base XML layout for a CardView and implemented methods in each subclass that would modify and return this CardView accordingly. Hence we used the principles of inheritance to reduce our code.
​
## Add
The add functionality of the app can be accessed by clicking the plus icon in the bottom right for each category (classes, assignments, exams, and to-dos). This directs the user to a form where they can add relevant information in the fields, leaving fields blank as desired. The type of form input is set to match the required type of data, such as multi-choice selection for the "Days of the week" field. Once the user saves their information, a pop-up message confirms if the save was successful, and the inputted information is displayed on the main page of each category.

The form data is used to instantiate a child class of the ActionItem object, which is added to an ArrayList that is shared across the different fragments in the app.

## Modify/Delete
The modify or delete functionality relies on keeping track of each CardView and buttons in them according to their index in the ArrayList that we maintain. Once a user clicks on the modify button the app confirms that the user wants to proceed and then redirects to the form while passing the ArrayList and the index of the above CardView. Once the form updates the ArrayList it returns it back to the display page where we then repopulate according to the new ArrayList. Similarly for the delete functionality as we are aware of the index of the Item we can directly remove items from the ArrayList and then repopulate the page once again with the new data.

https://github.com/maahirjain/college-scheduler-app/assets/140958721/af9d78c5-8a57-4084-a0d1-2e842e14934b

I worked on this project with two other peers at Georgia Tech.
