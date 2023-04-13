###  Course-content-management-system


## Design a system to help Instructors in authoring and maintaining course content. 
1. Course is 9 months long; divided into 9 Modules; each Module is 1 month long. (eg: Module = Machine Learning)
2. Module comprises Topics; each Topic is around 2 days of content. (eg: Topic = Linear Regression)
3. Topic consists of Pages; each Page is around 15 minutes of content. (eg: Page = Introduction to Linear Regression)
4. Page consists of an ordered list of Learning Items; a Learning Item is a single unit such as a video, a question, a PDF file, etc. (Items = [Video about Linear Regression, MCQ based on the video])
5. A new cohort of students is enrolled each month. 
6. Instructors may want to change/update the content at any time. Some changes should reflect     immediately across all batches that are using that item. But other changes should reflect only in the upcoming batches going forward.
7. Instructors should be able to clearly see which item is being used in which batch or module or
   topic or page. 
8. Instructors should be able to edit not just the content, but also the ordering of items in a
   topic, topics in a page, and pages in a module.
9. There could be thousands of learning items in a single course. 

. Design the system. Share which database, tools (CMS?), backend platform, etc. should be used and 
  what the architecture would look like.
  Design a sample database schema. 
  Design the workflow and how instructors should Instructors manage different variations of content across batches.

## Tools and Technologies:

    Backend Platform: Node.js
    Database: MongoDB

## Architecture:

.The system can be designed as a RESTful API that communicates with the CMS and the database. The 
 API will handle requests from the user interface and perform the necessary operations on the content stored in the database.


## Workflow:

    . Instructors can log in to the CMS and create a new course or select an existing course to edit.
   . Instructors can create modules, topics, pages, and learning items using the CMS. They can also reorder the items as needed.
    . The API will store the content in the MongoDB database.
    . When a new cohort is enrolled, the API will create a new instance of the course in the database with the current content.
    .Instructors can make changes to the content at any time using the CMS. If the changes should be reflected immediately across all batches, the API will update the existing instances of the course in the database. If the changes should only be reflected in upcoming batches, the API will update the content of the new instances of the course.
    . Instructors can view which items are being used in which batch, module, topic, or page using the CMS.

    ## Sample database schema:

# The MongoDB database can have the following collections:

   1. Course

    courseId
    courseName
    courseDescription
    startDate
    endDate


      2.Module

    moduleId
    courseId
    moduleName
    moduleDescription

     3.Topic

    topicId
    moduleId
    topicName
    topicDescription

     4. Page

    pageId
    topicId
    pageNumber
    pageTitle
    pageDescription

    5.LearningItem

    itemId
    pageId
    itemType
    itemTitle
    itemDescription
    itemOrder



## API:

# The API can have the following endpoints:

   . GET /courses - get all courses
   . POST /courses - create a new course
   . GET /courses/:courseId - get a course by id
   . PUT /courses/:courseId - update a course by id
   . DELETE /courses/:courseId - delete a course by id
   . GET /modules - get all modules for a course
   . POST /modules - create a new module for a course
   . GET /modules/:moduleId - get a module by id
   . PUT /modules/:moduleId - update a module by id
   . DELETE /modules/:moduleId - delete a module by id
   . GET /topics - get all topics for a module
   . POST /topics - create a new topic for a module
   .  GET /topics/:topicId - get a topic by id
   .  PUT /topics/:topicId - update a topic by id
   .  DELETE /topics/:topicId - delete a topic by id
   .  GET /pages - get all pages for a topic
   .  POST /pages - create a new page for a topic
   .  GET /pages/:pageId - get a page by id
   .  PUT /pages/:pageId - update a page by id
   .  DELETE /pages/:pageId - delete a page by id
   .  GET /items - get all learning items for a page
   .  POST /items - create a new learning item for a page
   .  GET /items/:itemId - get a learning item by id
   .  PUT /items/:itemId - update a learning item by id
   .  DELETE /items/:itemId - delete a learning item by id

   ## Tools & Technologies Used:

    Node.js
    Express.js
    MongoDB
    Mongoose ORM