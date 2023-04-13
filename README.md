###  Course-content-management-system


## Design a system to help Instructors in authoring and maintaining course content. 
1. Course is 9 months long; divided into 9 Modules; each Module is 1 month long. (eg: Module = Machine Learning)
2. Module comprises Topics; each Topic is around 2 days of content. (eg: Topic = Linear Regression)
3. Topic consists of Pages; each Page is around 15 minutes of content. (eg: Page = Introduction to Linear Regression)
4. Page consists of an ordered list of Learning Items; a Learning Item is a single unit such as a video, a question, a PDF file, etc. (Items = [Video about Linear Regression, MCQ based on the video])
5. A new cohort of students is enrolled each month. 
6. Instructors may want to change/update the content at any time. Some changes should reflect immediately across all batches that are using that item. But other changes should reflect only in the upcoming batches going forward.
7. Instructors should be able to clearly see which item is being used in which batch or module or topic or page. 
8. Instructors should be able to edit not just the content, but also the ordering of items in a topic, topics in a page, and pages in a module.
9. There could be thousands of learning items in a single course. 

Design the system. Share which database, tools (CMS?), backend platform, etc. should be used and what the architecture would look like.
Design a sample database schema. 
Design the workflow and how instructors should Instructors manage different variations of content across batches. 



. This is a web application designed to help instructors author and maintain course content. It allows instructors to organize content into modules, topics, pages, and learning items. Instructors can easily manage and update the content, as well as see which items are being used in which modules, topics, pages, and batches.
Features

    Divides the course into 9 modules, each consisting of topics, pages, and learning items
    Allows instructors to create, edit, and delete modules, topics, pages, and learning items
    Allows instructors to organize learning items into an ordered list within each page
    Provides a clear overview of which items are being used in which modules, topics, pages, and batches
    Supports immediate and future-only updates to content
    Provides a search function to quickly find specific learning items
    Can handle large amounts of content with ease

## Tech Stack

    Node.js for server-side JavaScript
    Express.js for building the web application
    MongoDB for the database
    Mongoose for object modeling
    React.js for the client-side user interface
    Material-UI for the design components

## Sample database schema:

The MongoDB database can have the following collections:

    Course

    courseId
    courseName
    courseDescription
    startDate
    endDate

    Module

    moduleId
    courseId
    moduleName
    moduleDescription

    Topic

    topicId
    moduleId
    topicName
    topicDescription

    Page

    pageId
    topicId
    pageNumber
    pageTitle
    pageDescription

    LearningItem

    itemId
    pageId
    itemType
    itemTitle
    itemDescription
    itemOrder

## Setup

    Clone the repository
    Install dependencies by running npm install
    Start the server by running npm start
    Navigate to http://localhost:3000 in your web browser

API Documentation

## The API endpoints are as follows:

    /api/modules
        GET: get a list of all modules
        POST: create a new module
    /api/modules/:moduleId
        GET: get a module by ID
        PUT: update a module by ID
        DELETE: delete a module by ID
    /api/topics
        GET: get a list of all topics
        POST: create a new topic
    /api/topics/:topicId
        GET: get a topic by ID
        PUT: update a topic by ID
        DELETE: delete a topic by ID
    /api/pages
        GET: get a list of all pages
        POST: create a new page
    /api/pages/:pageId
        GET: get a page by ID
        PUT: update a page by ID
        DELETE: delete a page by ID
    /api/learning-items
        GET: get a list of all learning items
        POST: create a new learning item
    /api/learning-items/:learningItemId
        GET: get a learning item by ID
        PUT: update a learning item by ID
        DELETE: delete a learning item by ID



        

For detailed documentation and examples, please refer to the API documentation included in the codebase.
## Conclusion

This course content management system provides a user-friendly interface for instructors to create, manage, and update course content. With its intuitive organization and search functionality, instructors can easily find and update specific items, while the system handles the complexities of managing content across multiple modules, topics, and pages.