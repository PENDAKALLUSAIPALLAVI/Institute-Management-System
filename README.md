1. Salesforce Developer Edition Setup:
---->I first created a Salesforce Developer Edition Org (free forever, for learning and building apps).
   
Steps:
---->Go to developer.salesforce.com/signup.
---->Enter details → Verify email → Login.

2. Custom Objects:
---->I identified the key entities needed for an Institute:
    Student – to store student details.
    Faculty – to store faculty details.
    Course – to store course details.
    Enrollment – junction object linking Students ↔ Courses.
    Fee Payment – to track fee payments of students.
Creation Steps:
---->In Setup, search Object Manager → Create → Custom Object.
Example (Student Object):
Label: Student
API Name: Student__c
Record Name: Student ID (Auto Number) with format STU-{0000}, starting at 1001.
Allow Reports, Activities, and Notes.
Save.

I repeated similar steps for Faculty, Course, Enrollment, and Fee Payment.

3. Fields (Custom Fields in Objects):
--->Each object was enhanced with fields:
Student: Full Name, Email, Phone, DOB, Enrollment Status, Course (Lookup → Course).
Faculty: Full Name, Email, Phone, Department.
Course: Course Name, Duration, Credits, Fees, Faculty (Lookup → Faculty).
Enrollment: Student (Lookup), Course (Lookup), Enrollment Date, Status, Grade.
Fee Payment: Student (Lookup), Payment Date, Amount, Mode of Payment, Status.

Steps to Create Fields:
Go to Object Manager → [Object] → Fields & Relationships → New.
Select field type (Text, Number, Currency, Lookup, Picklist).
Add field label, help text, and required status.
Save & add to Page Layout.

4. Tabs:
For each custom object, we created a Custom Tab so users can easily access it.

Steps:
Setup → Tabs → New → Custom Object Tab.
Choose the object (e.g., Student).
Pick an icon (e.g., book for courses).
Save.
Tabs created: Students, Faculty, Courses, Enrollments, Fee Payments.

5. Lightning App (Institute Management System App)

I created a dedicated Lightning App for IMS.

Steps:
Setup → App Manager → New Lightning App.
App Name: Institute Management App.
Added Navigation Items (Tabs): Students, Faculty, Courses, Enrollments, Fee Payments, Reports, Dashboards.
Added Utility Items (Notes, History, Chatter, Recent Items).
Saved and tested in App Launcher.
