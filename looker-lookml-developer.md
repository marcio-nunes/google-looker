# Looker LookML Developer

1. Introducing to Looker and LookML
2. Data Modeling Using LookML
3. Modeling Explores for your users
4. Working with derived tables

# 1. Introducing to Looker and LookML

- Recognize and articulate the value proposition of the Looker platform
- Recognize and articulate the value proposition for modeling data using the LookML modeling language

Looker is a Business Intelligence (BI) software and big data analytics platform that helps business users to explore, analyze and share real-time data analytics easily.

As a browser-based, Software as a Service (SaaS) platform, Looker connects directly to SQL databases.

- Other SaaS applications such as Salesforce, Mailchimp, and Zendesk.
- Heavy read-write operations in transactional databases such as Oracle, IBM Db2, and Microsoft SQL Server.
- Business planning tools such as SAP, NetSuite, and Oracle.
- And web analytics products such as Google Analytics or Adobe Analytics.
- Looker is multi-cloud and supports over 65 database dialects.

## Architecture

### Looker Agile Modeling Layer

One major benefit of Looker is its agile modeling layer, which can save data teams and business analysts time that would otherwise be spent manually writing and editing SQL queries. Looker’s agile modeling layer allows developers to define, through Looker Modeling Language or LookML, how the database is structured and how the tables and columns relate to each other. 

A useful way to think about LookML is that it is an abstraction layer for SQL that developers use to tell Looker what data to use from the connected database and how it should interpret that data. 

As users explore and analyze the data, Looker uses the defined LookML models to automatically generate SQL SELECTqueries to send to the database and return the appropriate results.

### Looker Data Governance

Another benefit of Looker is data governance, which means that you can define a single source of truth for data that everyone in the organization can understand and trust.

In Looker, you can enforce various types of data security and governance through the Looker User Interface (UI), such as assigning specific user roles, as well as through LookML, such as providing access to specific fields or rows of data. 

### Looker Data Democratization

To help organizations disseminate data, Looker can surface and expose query results in several ways. 

- **User Interface (UI)** - The first is through the web interface. This can be in the form of:
    - **Explores** - which are report-builder interfaces 
    - **Looks** - which are standalone reports or visualizations
    - **Dashboards** - which contain multiple visualizations
- **Data Scheduling and Delivery** - Another way is through scheduled data deliveries, such as sending Looks and dashboards to specific email addresses or Cloud
Storage buckets on a one-time or recurring basis.
- **Embeded Looker Content in your applications** - Explores, dashboards, and Looks can also be embedded within other websites or applications.
- **Looker API** -  Looker provides a REST API that allows you to retrieve,
analyze, and transform data and metadata directly from the Looker platform.
- **Looker's Rich Development Framework** - Looker's unique architecture provides a rich development framework that is built to support enterprise-grade workflows and
help your users and tools access the most accurate and up-to-date version of your organization’s data. With this unified view into your organization’s data, you, as a
LookML developer, can curate data experiences to ensure that both people and systems get the data they need, how and when they need it.

## Looker User Interface

- Recognize and detail the primary components of the Looker user interface
- Recognize and articulate the audience and purpose of the primary components of the Looker user interface

To understand how you as a LookML developer can support business users, it’s important to become familiar with the business user experience and how they use the Looker platform on a daily basis to answer data-driven questions. 

Furthermore, the ability to navigate the Looker platform as a business user will help you to fully test your changes to LookML code by reviewing how results appear when accessed by business users.

Folders in Looker are where content lives, just as files in your computer or Google Drive are stored in folders. 

As you may know, Looker has two primary categories of users: business users and developers. 

As a LookML developer, you use the Develop environment to curate report-builder interfaces called Explores that are used by business users and to configure other aspects in your Looker instance such as rules for caching and data security. 

Business users can click on Explore to see a list of the custom Explores that LookML developers have modeled for them. Within the Explores, they can analyze and visualize data to answer business questions and save their results as visualizations and reports. 

As a business user, you can also navigate through the various folders of the Looker instance to find content that has already been built using the available Explores.

The Explore, which is the report-builder interface that has been curated by a LookML developer. There are several expandable groups of fields in the field picker
found in the left-side panel. These are called views. An Explore is composed of one or more views.

In SQL terms, each view represents a database table, and the tables are pre-joined in the LookML model file to define the overall Explore.

Using this Explore, you can ask questions about your business. To see an information about the views, you can expand the view, and click on the dimension to add it to your
results set. Then, you can click Run to view the results. Behind the scenes, Looker has automatically generated a SQL query to bring the results from the database. As a LookML developer, you can click on the SQL tab — typically hidden from business users.

Rather than writing this SQL query manually, it was so easy for the business user to click on some fields and get this output automatically. This is all because of the agile modeling layer in LookML.

A LookML developer or team of developers had already created this Explore, specified which views should be in the Explore, specified which dimensions and measures should be in each view, and defined the SQL logic for each dimension and measure.

That was a quick demonstration of the significance and value of LookML for empowering business users to explore and analyze data. 

A Looker administrator needs to create a connection to a specific data source such as your company’s primary database, in order for LookML developers to access and model that data to curate Explores for business users.

Admins can find setup and configuration details in the Database configuration details section of Looker’s dialects documentation page. 

As a LookML developer, you can see available database connections in your organization’s Looker instance by clicking on the Develop tab in left-side navigation panel of the Looker UI, then, selecting SQL Runner.

**SQL Runner** is a console or portal to the databases that have been connected to your organization’s Looker instance. You can see all of the database connection options under Connection.

## The Looker IDE

- Recognize and define the purpose of the Looker Integrated Development Environment (IDE)
- Recognize and identify where in the Looker platform UI the IDE resides
- Recognize and articulate how LookML developers write code in the IDE

Looker provides an integrated development environment (IDE) that developers can use to modify existing and to model new dimensions, measures and Explores for business users to employ in their data analysis approaches.

### Production Mode vs Development Mode

In Looker, business users interact with and experience the Looker instance in production mode while developers make changes and test new features through development mode.

Production mode uses the latest production version of Looker. Everyone using a Looker instance in production mode accesses its projects, Explores, and content in the same state.
LookML project files are read-only in this mode.

As a LookML developer, you can use development mode to make changes to projects without affecting anyone else. Development mode accesses a completely separate version of
your project files that only you can see and edit.

If you are familiar with Git, production mode uses the main branch of the Git repository of the LookML project while development mode uses a separate branch created from
the main branch. After testing, changes made by LookML developers in the separate branch can be merged into production, so that all users of the Looker instance can access the updates.

### Dev Mode

When you are in working in development mode, Looker will display a blue banner at top of the Looker User Interface (or UI) with a message that you are in development mode. 

One option is to use the toggle button at the bottom left-side of the Looker UI to enter Development Mode. You can also use the same toggle button to exit Development Mode and return to production mode.

There is also a keyboard shortcut: Control+Shift+D.

Alternatively, at the top left-side of the Looker User Interface, you can click on Develop menu to see the options, and then select Projects. Then, once you are on the Projects page, you can turn on Development Mode by clicking on the Develop option from the top menu bar and using the toggle button for Development Mode. 

### IDE

From the Projects page, you can also click on a specific project name such as training_ecommerce to open it within the Looker Integrated development environment (IDE).

An IDE is an industry term for an application in which software engineers or developers can write and test their code. 

The Looker IDE displays six navigation options on the left-side panel:

- **The folder icon** - is the file browser. This displays all the LookML project files in the folder hierarchy.
- **The compass icon** - is the object browser. The object browser organizes project files by LookML object type in the project. Each model can be expanded to show the Explores within. 
    - Each Explore can be expanded to reveal the views that are joined together.
        - Each view can be expanded to display the dimensions and measures. 
- **The find-and-replace option** - You can search for a specific word like “count” and see where and how many times this term appears throughout all the files in your entire  project. You can also batch-replace all instances of a text string with something else.
- **The Git actions** - These options allow you to switch between Git branches, view past commits by yourself and fellow developers, view the project on GitHub, or whichever Git provider you use at your company, and more.
- **The project settings** - As a LookML developer, you can see the configurations, but only a Looker admin can change them. For example, admins can specify what is or isn’t required to commit code, enable pull requests if your team prefers to do code reviews before deploying to production, change the Git connection, and more. 
- **The deployment manager** - This page lets you see the recent changes that have been deployed to the production environment. Additional details about the changes, such as the user and date associated with the change, are also available on this page.

In summary, as a LookML developer, you can make and test changes in your organization’s Looker instance in development mode, without impacting the production environment.

When working in your organization’s Looker instance, be mindful of whether you are currently in production mode or development mode. The Looker IDE and Explore menus will offer a few different features and options in production vs. development mode. Depending on your permissions and local code differences, you may even see different lists of projects, project files, and Explores.

## LookML Project Version Control

- Recognize and interpret at a high level how Looker integrates with the Git version control system
- Recognize and articulate the process by which LookML developers write, validate, merge, and ultimately deploy their code

### Git

Git is a widely used version-control system for multiple programmers to collaborate on the same library of code. Through Looker’s integration with Git, you can make and test changes locally first in Looker’s integrated development environment (or IDE), and then send your changes to the primary production environment after the changes have been tested locally. 

This version control process allows you to collaborate on one project with other developers who can receive your updates as well as share their updates with you.

To understand how version control with Git works, it is helpful to think of the Git repository for a LookML project as a tree. New LookML code is always written in a branch of the tree. The main production code that is live would be the trunk of the tree, while each developer creates a branch from the trunk to create and test new objects such as dimensions, measures, Explores and more.

After changes have been tested locally in a branch, the LookML developer can send the changes to the trunk, or the production environment for the LookML project. After that point, other developers can pull changes from the trunk to their branches of the project.

Git is commonly managed through a third-party provider such as GitHub, Bitbucket, or GitLab. To configure Git, you need a URL or connection string for the repository that you would like to use.

The Git configuration is typically completed by a Looker team lead or administrator and only has to be completed once per LookML project. The lead or administrator will set up the GitHub repository to allow write access from the LookML developers, so that all of them can sync changes to and from the primary production repository on GitHub. 

One key point that you need to know as a LookML developer is that when you enter Development Mode, Looker automatically creates a local branch for you to make and test changes. This branch can be only be modified by you, though developers with access to the same project can view others’ branches if they like. The Looker IDE will alway display which branch you are working in, at the top of the page next to the project name.

On the Git Actions page, you can also view others’ branches in read-only mode, or even create new branches or even sharedbranches, also known as feature branches. You may want to create a new branch if you have only partially completed a large workflow on your own branch, and you need to develop and deploy an unrelated change without sending all of your other code changes to the production environment.

Shared branches are useful for allowing multiple developers to collaborate on the same version of code to implement a new feature or bug fix. The shared branch can easily be deleted once the collaboration is complete. 

Another key concept for developers to remember is that all changes made in development mode remain in the active development branch until they are pushed to production. So you
can continue to make and test changes to LookML code in development mode without having to push these changes to production until you are ready. 

Depending on the settings configured by the administrator of you organization’s Looker instance, you may have access to send your changes directly to production. While by default LookML developers can merge and deploy their changes to production, Looker administrators can choose to restrict the deployment of changes to production by configuring projects to use pull requests using the Configuration options on the Project Settingspage. 

When pull requests are enabled, developers submit pull requests to notify others that they want to submit changes to the production code. Another team member (usually a lead or designated reviewer) reviews the pull request in the Git provider (such as github.com), and if they approve the changes, they can choose to merge the changes to production.

While you are working in your branch, you may decide that you no longer want to save the changes that you have been making. Luckily, in the Looker IDE, you can revert any changes made in development mode that have not been pushed to production by using the Revert to options on the Git Actions page. This action will undo all uncommitted changes, so that you can start over with a clean branch that matches the latest production environment.

In summary, when you enter development mode, Looker will automatically create a local branch for you to make and test changes. The branch that you are currently working in will always be displayed at the top of the Looker IDE. You can see additional information about your branch and access different options under the Git Actions page of the IDE.

All changes made in development mode will remain in development mode until they are merged to production. Depending on the settings configured by your Looker admin, you may have
permission to directly merge your changes to production, or you may have to submit a pull request for someone else to review and approve your changes.

### Exemple of Git Workflow in Looker

Begin by enabling Development Mode using the toggle button for Development Mode in the bottom left corner of the Looker home page. Then, click Develop on the left side navigation menu.

Within the Develop options, click on the project.

A best practice when working in a new branch is to first pull changes from production to your local branch, to ensure that you have the most recent version of all project files. You can pull changes from production by clicking the Pull from…option on the Git Actions page. In the window that opens, select Pull from Production. After you have pulled the updates from production, you are ready to start writing new LookML code in your current development branch.

As you make changes in your branch, the button in the top right corner of the IDE will display the next step that is needed in the Git workflow.

A greyed out status of **Up to Date** indicates that the branch matches the production environment. This means that your current branch contains all changes previously sent to the production environment and that new no changes have been made yet in your branch.

When you do make a new change in your branch, a button labeled **Save Changes** will appear in the top right of the code window. Be sure to save your changes often. If you have made changes in a file without saving them, you will prompted to save your changes before you navigate to other files in your project. 

As you save changes to a file (such as adding, editing, or removing code), a blue dot will appear next to the name of the modified LookML file in the File Browser. This makes it easy for you to see where you have been making changes in your branch.

After you save your changes, you will be prompted to validate the changes by selecting **Validate LookML**. This ensures that your changes include valid LookML code. If the initial validation identifies errors, you can resolve the errors, save your changes, and validate the changes again. 

After validating your LookML code, the next step in the Git workflow is to Commit Changes & Push changes to your branch. This step completes two actions: first it commits your changes to the local .git folder, where local versioning takes place. Then, it pushes your local branch to sync with your remote branch on the external Git repository (which would be in a third-party tool such as GitHub).

While this step makes the validated LookML code from your branch available on the remote Git repository such as GitHub, the changes are not available yet to the business users—there’s one more step we’ll see next to deploy the changes to production. 

After you click on Commit Changes & Push, a new window will open in the IDE with a list of the files that were modified. In this Commit window, it is a best practice to include a short comment explaining the changes that were made in the commit.

The last step in the Git workflow is to Merge to Primary Branch. This action will deploy your changes to production, where business users will see your changes immediately.
Depending on the settings configured by your Looker admin, you may not see this option if you do not have permission to directly merge your changes to production. In that case, you would submit a pull request for someone else to review and approve your changes.

If you do have the sufficient permissions but still do not see the option to merge and deploy, then you likely have encountered a merge conflict that needs to be resolved. A merge conflict means that another developer recently committed some code that conflicts with yours. Perhaps you both tried to edit line 10 of the same view file.

You will need to review the conflicting files (highlighted in the file browser), choose which changes to keep, and then commit again to receive the option to merge and deploy. 

After you successfully merge and deploy your changes to production, the Looker IDE will once again display an Up to Datestatus.

## How Looker Writes SQL

- Recognize and articulate how Looker reads, parses and writes SQL
- Recognize and define the relationship between SQL and Looker’s LookML modeling language

As a LookML developer, you can define as many dimensions and measures as you like in your view files to curate data. Remember though, for business users to leverage these dimensions and measures, you need to make them available through Explores. To create Explores, it is helpful to first understand how Looker generates SQL before learning how to work with the model file within your project. 

All SQL queries in Looker begin with the data and options that business users select from the Explore. When users click the run button, Looker automatically generates and sends the necessary SQL to the underlying database, and then returns the results to the user. 

As a LookML developer, you can see the SQL query generated by Looker and then sent to the underlying database in the SQL window.

To summarize, the dimensions selected by business users are listed in the SELECT statement of the generated SQL query, while the selected measures appear in the SELECT statement as aggregating functions, such as count, applied to dimensions. In the SQL query, the base view of an Explore is always selected first, and other needed views are joined based on users’ selections; unnecessary views in the Explore are not joined in the SQL query. 

As the users select filters and update limits in the Explore, those re also reflected in the generated SQL query using the WHERE, HAVING, and LIMIT clauses. Now after this deep dive into the SQL queries generated by Looker, you are ready to leverage Looker-generated SQL to design Explores for your business users. 

# 2. Data Modeling Using LookML

## Anatomy of a LookML project

LookML stands for Looker Modeling Language. It is Looker’s proprietary language that establishes an abstraction layer for SQL. Developers use LookML to tell Looker what data to use from the connected database and how it should interpret that data. 

Specifically, LookML acts as the modeling layer between the connected SQL database and your business users. Looker uses the LookML code written by developers to define how business users interact with a connected database and to construct SQL queries against that particular database. 

Developers use LookML to define many items from the connected SQL database including data attributes called dimensions, aggregates of dimensions called measures, data relationships such as how to join tables, and custom tables and fields.

A key concept of LookML to remember is: If it’s possible in your SQL dialect, it should be possible in Looker.

### Hierarchy of LookML objects

For full comprehension of the key LookML terms, developers need to understand where each object fits into the overall hierarchy of a LookML project.

- **LookML Project** - The highest level, is a library of self-contained LookML code. Because Looker uses Git for version control, a best practice is for each project to map one-to-one with a dedicated Git repository. A project is essentially a library of code for a specific data source or database connection and contains one or more data models.
You can think of each project as an semi-independent or miniinstance of Looker, and each project should map one-to-one to a Git repository for version control. 
- **Models** - As previously mentioned, a LookML project is composed of one or more models. A model specifies a database connection and the data views that utilize that connection. Specifically, a model file is used to define:
    - The database connection.
    - The view files that are accessible to this model.
    - The Explores (which are pre-joined views) and their join logic.
- **Explores** - which are sets of pre-joined views organized by business area defined within the model files. Explores are the central component of Looker that allow business and data analysts to conduct self-serve data exploration, analysis, and visualization. Within a model file, developers define Explores that join one or more views together to target specific questions that business users may have. So you can think of an Explore as a predefined set of tables that would frequently be joined for business inquiries and use cases.
- **Views** that are joined in the Explores represent the underlying database tables. Within view files, developers can define the dimensions (or data attributes) and measures (or aggregations of attributes) to provide to business users in the Explore interface. 
- **Dimensions and measures** 
    - Dimensions are data attributes and represent the fields or column of a database table. When the view files are generated from a table by Looker, dimensions are automatically created for any columns that already exist within your database tables. You can also create additional dimensions that would serve as logical representations of table columns. 
    - Measures are aggregates of dimensions and do not live explicitly in your database tables. They must be created using LookML. They aggregate dimensions into values like sums or counts. 

To recap, a LookML project is a library of code that models a data source and should map 1:1 to a Git repository for version control.

Projects contain model files, which define the Explores that should be packaged together, how those Explores work, and which views are joined in which Explores. 

View files describe database tables or logical representations of them and are joined together to define Explores in the model files.

Views are then accessed by business users through the Explore to query data and create reports and visualizations.

Dimensions and measures are defined within view files. Dimensions are attributes of data and represent fields or columns in the database tables, while measures are aggregates of
dimensions such as a count or sum. 

## Modeling dimensions

- Recognize and detail the steps and conditions necessary to create a dimension used in an Explore in Looker
- Recognize and identify where in the Looker UI LookML developers can create a dimension
- Recognize and articulate the relationship between the dimensions you create in the Looker IDE and the dimensions that data viewers, decision makers, and business analysts
use in Explores in Looker

In Looker, dimensions are qualities or attributes of your data. Typically, each dimension represents a column in your underlying database.  

### Referencing tables

```
dimension: first_name {
    type: string
    sql: ${TABLE}.first_name ;;
}
```

When Looker generates a new view file from a table, it automatically creates dimensions for every column (or field) in the database table.

Auto-generated dimensions have a sqlparameter containing the word TABLE highlighted in blue, with a dollar sign and curly braces, such as: sql: ${TABLE}.first_name

**${TABLE}** references the table specified in the **sql_table_name** parameter at the top of your view file. This lets Looker know which database table to use as the default table when pulling the dimensions and measures.

### Referencing objects

```
dimension: full_name {
    type: string
    sql: CONCAT(${first_name}, ' ', ${last_name}) ;;
}
```

Another version of the substitution syntax is using an existing dimension or measure name within curly braces, preceded by a dollar sign, such as: sql: ${field_name}

Referencing the Looker object is better than the hard-coded database column, so that the new field inherits any transformations or additional logic from the overall dimension. It also reduces the number of times or places you’ll need to make updates if something like the database column name changes.

### Dimesions types

In Looker, there are four common dimension types:

- **String** - used for text.
- **Number** - used for columns of numeric data types such as int, decimal, or float.
- **yesno** - used for Boolean.
- **Tier** - are useful for bucketing values. When defining a new tier dimension, you need to use the tiersparameter to indicate which buckets you want to assign. Each comma-separated number will be the start of a range. For example, a 0 followed by 30 means that there is a first bin containing the values from 0 to 29, followed by a second bin beginning at 30, and so on.
    - There is also a **style** parameter where you can specify how you want the results to be formatted for business users, such as integer to display the bin range as whole numbers or relational to display a text expressions that include symbols such as less than (<) or greater than (>). 

```
dimension: first_name {
    type: string
    sql: ${TABLE}.first_name ;;
}
dimension: age {
    type: number
    sql: ${TABLE}.age ;;
}
dimension: is_new_customer {
    type: yesno
    sql: ${days_since_signup} <= 90 ;;
}
dimension: age_tier {
    type: tier
    tiers: [18, 25, 35, 45, 55, 65, 75, 90]
    sql: ${age} ;;
    style: integer
}
```

### Dimesions groups: Time

For these dimension groups, you use the timeframesparameter to specify the date and time parts required for the data. There are many options for the timeframe, such as hour, day_of_week, month, quarter, or year. 

The number of dimension fields created within a dimension group is dependent on the number of timeframes listed in the timeframes parameter. For example, including only date, hour, month, and year will result in only these four dimension fields created as part of the dimension group.

When generating new view files from tables, Looker will automatically create dimension groups for most date and time columns; though, it is possible for some formats to not be
automatically recognized by Looker.

```
dimension_group: created {
    type: time
    timeframes: [raw, time, date, hour, hour_of_week_index, week, month_num, month, year, Quarter, quarter_of_year]
    sql: ${TABLE}.created_at ;;
}
```

When using an existing dimension group timeframe to define another dimension—for example, in a dimension performing a DATE_DIFF() or difference between two dates—you can specify
the desired date or time unit to identify the date field from the dimension group. In this example, a new dimension named shipping_days is created based on the difference between the ${shipped_date}and the${created_date} in number of days.

```
dimension: shipping_days {
    type: number
    sql: DATEDIFF(${created_date}, DAY) ;;
}
```

### Dimesions groups: Duration

Using the intervals parameter, you can allow business users to choose from a range of time intervals. When possible, a best practice is to create dimension groups of
type duration instead of defining dimensions that perform DATE_DIFF() functions in the sql parameter. This allows you to avoid hard-coding the date part, so your business users can choose what works best for them. 

Additionally, this prompts Looker to write the function for you, which is easier if you’re not as comfortable with SQL, and it will create less work for you in the future, in case your company ever decides to change the underlying data source.

```
dimension_group: enrolled {
    type: duration
    intervals: [second, minute, hour,day, week, month, quarter, year]
    sql_start: ${TABLE}.enrollment_date ;;
    sql_end: ${TABLE}.graduation_date ;;
}
```

To reference one of these fields, use: **${hours_enrolled}**, **${days_enrolled}**, **${years_enrolled}**, etc.

In conclusion, there are many dimension types in Looker including string, number, yesno, tier, and dimension groups for time and duration. 

When referencing a column from a database table for the first time in a LookML model, use **${TABLE}**. When defining new dimensions that build on existing ones, you can reduce the instances of hard-coding column names by using the **${field_name}** substitution operator to reference the existing LookML object.

### Lab

### Task #1 - Place Looker in Development mode

In this task, place Looker into Development mode.

1. Locate the Development Mode toggle in the immediate lower-left corner of the user interface.
2. Click the toggle to activate Development mode. (LookML development can ONLY be performed in Development mode.)
3. The blue bar now at the top of your screen indicates you are in Development mode.

### Task #2 - Create a city-state dimension in the users.view view file

In this task, write LookML code to create a city-state dimension in the users.view view file.

1. From the Develop menu in the left-hand navigation panel, select the qwiklabs-ecommerce LookML project.
2. Under the views section, choose the users view (users.view) to edit.
3. Within users.view after the last listed dimension and before the first measure, create a new dimension that combines City and State into a single field. 
4. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will notice a blue dot next to the users.view view file now in the File Browser.

```
dimension: city_state {
    type: string
    sql: ${city} || ', ' || ${state};;
}

Or

dimension: city_state {
    type: string
    sql: CONCAT(${city}, ', ', ${state});;
}
```

### Task #3 - Create a shipping days dimension in the orders_items view file

In this task, write LookML code to create a shipping days dimension in the orders_items.view view file.

1. From the Develop menu in the left-hand navigation panel, select the qwiklabs-ecommerce LookML project.
2. Under the views section, choose the order_items view (order_items.view) to edit.
3. Within order_items.view, create a Shipping Days dimension that calculates the number of days between the order ship date and the order delivered date. 
4. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will notice a blue dot next to the order_items.view view file now in the File Browser.

```
dimension: shipping_days {
    type: number
    sql: DATEDIFF(day, ${shipped_date}	,${delivered_date});;
}
dimension_group: shipping_days {
    type: duration
    sql_start: ${shipped_date};;
    sql_end: ${delivered_date};;
    intervals: [day]
}
```

### Task #4 - Create a traffic source email dimension in the users.view view file

In this task, write LookML code to create a traffic source dimension in the users.view view file.

1. From the Develop menu in the left-hand navigation panel, select the qwiklabs-ecommerce LookML project.
2. Under the views section, choose the users view (users.view) to edit.
3. Within users.view, create a new dimension that calculates whether the Traffic Source that brought in a given user was via “Email” or not. Your solution should include the yesno dimension type.
4. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will continue to notice a blue dot next to the users.view view file in the File Browser.

```
dimension: is_email_source {
    type: yesno
    sql: ${traffic_source} = 'Email' ;;
}
```

### Task #5 - Create an age group dimension in users.view view file

In this task, write LookML code to create a age group dimension in the users.view view file.

1. From the Develop menu in the left-hand navigation panel, select the qwiklabs-ecommerce LookML project.
2. Under the views section, choose the users view (users.view) to edit.
3. Within users.view, create a dimension that groups individual ages into the following age group buckets: 18, 25, 35, 45, 55, 65, 75, 90. 
4. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will continue to notice a blue dot next to the users.view view file in the File Browser.

```
dimension: age_tier {
    type: tier
    tiers: [18, 25, 35, 45, 55, 65, 75, 90]
    sql: ${age} ;;
    style: integer
}
```

### Task #6 - Push your changes to the Git repository

In this task, you will commit the code changes you made to your Looker student git repository.

1. With all your LookML changes to the users.view and order_items.view view files saved, click the Project Health icon in the top-right corner of the window.
2. In the Project Health > LookML validation section, click Validate LookML icon.
3. If it shows No LookML errors found, click the Commit Changes & Push button to push your changes to the repository.
4. You will be asked to include a commit message so other developers will understand what changes you’ve made, so write “Added dimensions to users.view and order_items.view” for your commit message and click Commit.
5. When that process completes, you’ll be presented with a new button that says Deploy to Production. Click this button to deploy your new LookML code.

## Modeling measures

- Recognize and detail the steps and conditions necessary to create a measure used in an Explore in Looker
- Recognize and identify where in the Looker UI LookML developers can create a measure
- Recognize and articulate the relationship between the measures you create in the Looker IDE and the measures that data viewers, decision makers, and business analysts use in Explores in Looker

In Looker, dimensions represent the data attributes in a database table, whereas measures are ways to perform aggregate functions, such as a count, on the dimensions.

Whenever you define new dimensions and measures that build on existing ones, it is a best practice in Looker to use ${field_name} to reference existing LookML objects.

```
measure: name_of_measure {
    type: measure_type
    sql: ${field_name} ;;
}
```

### Measure types

- **Sum** - aggregates the values in a specified dimension by adding all values together to calculate a total value.
- **Average** - the mean value of the specified dimension.
- **Count** - if you use Looker to generate your model files from a data source, your model’s view files will already contain a default measure for the count of rows. This count does not use the sql parameter; instead, it will simply use the view’s primary key as the dimension to aggregate.
- **Count Distinct** - If you want to count something other than the view’s primary key, you need to use the measure type called count_distinct. This type does allow you to input a sql parameter for the dimension you want to count.

```
dimension: sale_price {
    type: number
    sql: ${TABLE}.sale_price ;;
}
measure: total_revenue {
    type: sum
    sql: ${sale_price} ;;
    value_format_name: usd_0
}
measure: average_sale_price {
    type: average
    sql: ${sale_price} ;;
}
measure: count_items_ordered {
    type: count
}
measure: count_users {
    type: count_distinct
    sql: ${user_id} ;;
}
```

In summary, there are three primary measure types in Looker including sum, average, and count. To define a new measure, use the sql parameter to specify which dimensions you want to aggregate, and then define a way to aggregate them using the type parameter.

## Dimension and measure modeling logic

- Recognize and articulate how to model some additional dimensions with more complex behaviors for end users in Looker
- Recognize and articulate how to model some additional measures with more complex behaviors for end users in Looker
- Recognize and identify where in the Looker UI LookML developers can create dimensions and measures

LookML provides advanced logic options that you can use when you define dimensions and measures. 

### Referencing fields in other views

Simply write the view name and a period before the field name, all within the curly braces following a dollar sign, such as: **${inventory_items.cost}**

```
dimension: profit {
    type: number
    sql: ${sale_price} - ${inventory_items.cost} ;;
}
```

> Keep in mind, though, that in order for this syntax to work correctly, the two views involved need to be joined together in an Explore.

### Filtered measures

A useful parameter for defining measures is the filtersparameter, which you can use to create measures based on specific dimension values.

```
measure: count_usa_users {
    type: count
    filters: [country: "USA"]
}
```

> Take note though that although the filters parameter does not use the familiar substitution syntax of ${field_name}, the field names still actually refer to existing LookML dimensions, not the literal database column names.

### Using measures to define other measures

Now, just as you can reference existing dimensions when creating new measures, you can also reference previously-modeled measures when defining a new measure. For example, your new measure could include multiple measures interacting with each other, such as calculating the percentage of users located in a specific country, out of the total number of users.

```
measure: percentage_usa_users {
    type: number
    value_format_name: percent_1
    sql: 1.0 * ${count_usa_users}/NULLIF(${count}, 0) ;;
}
```

> Please remember though that whenever you want to include other measures in the sql parameter of a new measure, you need to use the measure type called number. 

### Filtered measures

The filter is based on an existing yesno dimension named is_new_user. Only rows that return a value of “Yes” for this dimension are summed across the sales_price dimension for a sum of sales to only new users.

```
measure: count_usa_users {
    type: count
    filters: [country: "USA"]
}
measure: total_sales_new_users {
    type: sum
    sql: ${sale_price} ;;
    filters: [users.is_new_user: "Yes"]
}
```

> Both of these examples would generate a CASE statement (in other words, if/then/else) within the aggregate function of the SQL query.

In summary, LookML provides several options for advanced logic when defining custom dimensions and measures. As demonstrated through these examples, you can reference fields in other views, use measures to define other measures, and use dimensions to filter measures.

## LookML dashboards

### Convert a user-defined dashboard into a LookML dashboard

In this task, make a copy of a user-defined (created) dashboard and then convert it into a LookML-based dashboard. Make sure you are in development mode.

1. Return to your dashboard.
2. Click the three-dot menu at the right and select Get LookML.
3. Use the Copy to Clipboard link in the bottom left-hand section of the pop-up to copy all the dashboard LookML.
4. From the Develop menu in the left-hand navigation panel, select a LookML project.
5. From the left-hand side File Browser, click on the plus sign and choose the Create dashboard menu option.
6. Name your new LookML dashboard.
7. Remove the autogenerated dashboard LookML and paste in the copied dashboard LookML.
8. Save the dashboard.
9. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will notice a blue dot next to dash_name.dashboard.lookml now in the File Browser.
10. Push your changes to the Looker Git repository. 

### Modify a LookML dashboard

In this task, make specific modifications to an existing Look ML dashboard.

1. Ensure you are still in Development Mode.
2. From the Develop menu in the left-hand navigation panel, select a LookML project.
3. Within the LookML project files, locate dash_name.dashboard.
4. Make changes.
6. Click the Save button on your visualization changes to commit them.
8. Save your changes by clicking the blue “Save Changes” button at the top-right of the editor. You will notice a blue dot next to dash_name.dashboard now in the File Browser.
9. Push your changes to the Looker Git repository

# 3. Modeling Explores for your users

- Recognize and detail the steps and conditions necessary to model a new Explore using the Looker IDE
- Recognize and identify where in the Looker UI LookML developers can model an Explore
- Recognize and articulate the relationship between the Explores you model in the Looker IDE and the Explores that data viewers, decision makers, and business analysts use in Looker

In Looker, Explores can be thought of a set of tables with predefined join logic. As a LookML developer, you define and curate Explores for users at your organization to analyze data and answer their business questions. 

Within the model file of a project, you can define Explores similarly to how you define dimensions and measures: by typing the word “explore” followed by a colon (:), and giving it a name. 

> Unlike dimensions and measures, which can be named however you like, the name of the Explore must be the name of an actual view file. 

```
explore: base_view {
    join: order_view {
        type: left_outer
        sql_on: ${base_view.id} = ${order_view.column_id} ;;
        relationship: one_to_many
  	}
}
```

To understand how to define explores, let’s review the key parameters within the explore definitions in a model file. First, the **explore** name establishes the base view, meaning that it is the central view for analysis in the Explore. Other views joined to this Explore provide additional or supplemental analysis capabilities. 

You need to define a join in the explore definition using the **join** parameter. 

Then, you need to provide a value for the type parameter to identify the join type between the views.

The four types of joins available in Looker are: **left_outer**, **inner**, **full_outer**, and **cross**. If no type is provided, the default type applied is **left_outer**. 

- **left_outer** join means that all records in the left-side view of the join will be retained, even if there is not a match with any records in the right-side view of the join. 
- **inner join** means only matched records between the two views will be retained.
- **full_outer** means all records in both views will be retained whether or not there is a match in the other view.
- **cross join** generates a paired combination of all rows across both views, independent of whether records match or not. 

After defining the join table and type, you need to provide the data fields for the join using the **sql_on** parameter. Typically, you join two tables using a dimension from one view that is the same as a dimension in the other view. 

Last, the relationship parameter describes the cardinality between the two views, meaning how many records could potentially be matched between the views based on the fields
identified in the sql_on parameter. In Looker, the options for relationships are **one-to-one**, **one-to-many**, **many-to-one**, or **many-to-many**. If no relationship parameter is provided, the default relationship applied is **many_to_one**.

- **One-to-one** indicates that each record in both views has only one matching record in the other table. 
- **Many-to-one & one-to-many** - Many-to-one indicates that there may be many records from the first view that are connected to only one record in the second view table, and vice versa for one-to-many. 
- **Many-to-many** means that there could be multiple records in the left view that match multiple records in the right view.

**Standard joins** - As the name of the Explore is also the base view, it is always in the FROM clause of any SQL query generated in the Explore. Joins defined directly to the base view of an Explore are referred to as standard joins.

Sometimes you may need to join the same table twice in an Explore. In the world of manually writing SQL queries, you would give the two tables different aliases. In LookML, you can do this by providing a unique name for the join, and then referencing the actual view name to be joined in the from parameter. 

In this example, the joins named aircraft_origin and aircraft_destination are both joining the same views named flights and airports to provide different information: one join for the origin location and another join for the destination location. The names of the joins use alias names, while the fromparameter both specify airports. Notice that the sql_on parameter uses the alias names as well. 

```
explore: flights {
    join: carriers {
        type: left_outer
        sql_on: ${flights.carrier} = ${carriers.code} ;;
        relationship: many_to_one
    }

    join: aircraft {
        type: left_outer
        sql_on: ${flights.tail_num} = ${aircraft.tail_num} ;;
        relationship: many_to_one
    }
-------------------------------------------------------------------------
>   join: aircraft_origin {
>       from: airports
        type: left_outer
>       sql_on: ${flights.origin} = ${aircraft_origin.code} ;;
        relationship: many_to_one
        fields: [full_name, city, state, code, map_location]
    }

>   join: aircraft_destination {
>       from: airports
        type: left_outer
>       sql_on: ${flights.destination} = ${aircraft_destination.code} ;;
        relationship: many_to_one
        fields: [full_name, city, state, code]
    }
-------------------------------------------------------------------------
    join: aircraft_flight_facts {
        view_label: "Aircraft"
        type: left_outer
        sql_on: ${flights.tail_num} = ${aircraft_flight_facts.tail_num} ;;
        relationship: one_to_one
        fields: [full_name, city, state, code]
    }
}
```

**Indirect joins** - You can also write indirect joins that do not join to the base view; instead, they join to another view in the Explore that is already joined to the base view. Indirect joins can be useful when there is no shared join key with the base view but can potentially impact performance. 

In this example, the join aircraft_flight_facts does not join to the base view called flights; instead, it joins to aircraft, which is referenced in the second join in this Explore. Any time a business user has an inquiry involving aircraft_flight_facts, the generated SQL query will first select FROM flights and then join to aircraft—even if no fields or filters are needed from aircraft itself—so that it can then join to aircraft_flight_facts. 

```
explore: flights {
    join: carriers {
        type: left_outer
        sql_on: ${flights.carrier} = ${carriers.code} ;;
        relationship: many_to_one
    }
-------------------------------------------------------------------------
>   join: aircraft {
-------------------------------------------------------------------------
        type: left_outer
        sql_on: ${flights.tail_num} = ${aircraft.tail_num} ;;
        relationship: many_to_one
    }

   join: aircraft_origin {
        from: airports
        type: left_outer
        sql_on: ${flights.origin} = ${aircraft_origin.code} ;;
        relationship: many_to_one
        fields: [full_name, city, state, code, map_location]
    }

    join: aircraft_destination {
        from: airports
        type: left_outer
        sql_on: ${flights.destination} = ${aircraft_destination.code} ;;
        relationship: many_to_one
        fields: [full_name, city, state, code]
    }

    join: aircraft_flight_facts {
        view_label: "Aircraft"
        type: left_outer
-------------------------------------------------------------------------
>       sql_on: ${flights.tail_num} = ${aircraft_flight_facts.tail_num} ;;   <- Indirect Join
-------------------------------------------------------------------------
        relationship: one_to_one
        fields: [full_name, city, state, code]
    }
}
```

> So due to the extra join, we recommend that you aim to use a join key from the base view when possible, rather than using indirect joins. 

Here is an example SQL query you might have needed to write by hand before using Looker. Imagine that you want to get the number of canceled flights whose aircraft originated in the state of California as well as some additional details about these canceled flights such as flight destination, aircraft name, and aircraft origin.

```SQL
SELECT 
    flights.destination AS flights_destination,
    aircraft.name AS aircraft_name,
    aircraft_origin.city AS aircraft_origin,
    count(*) AS flight_count
FROM training.faa.flights AS flights

LEFT JOIN training.faa.aircraft AS aircraft
    ON flights.tail_num = aircraft.tail_num

LEFT JOIN training.faa.airports AS aircraft_origin
    ON flights.origin = aircraft_origin.code

WHERE (flights.canceled = TRUE) AND (aircraft_origin.state = 'CA')
GROUP BY 1, 2, 3 
```

Same query in LookML Explore.

```LookML Explore
explore: flights {
    join: aircraft {
        type: left_outer
        sql_on: ${flights.tail_num} = ${aircraft.tail_num} ;;
        relationship: many_to_one
    }

    join: aircraft_origin {
        from: airports
        type: left_outer
        sql_on: ${flights.origin} = ${aircraft_origin.code} ;;
        relationship: many_to_one
    }
```

By leveraging your pre-defined Explore logic, Looker empowers self-serve analysis and exploration by your business users, which saves you time and resources as a LookML developer.

In summary, as a LookML developer, you define the Explores for business users within the model file of a project. The name of the Explore must be the name of an actual view file, and you can define joins to other views in your model to provide additional details in the Explore. To define a new join, use the joinparameter to name the join, typically the same name as the actual view file. Then, use the type parameter to identify how the two views should be joined, such as left_outer.

The sql_on parameter identifies the shared column that is being used to join the tables, while the relationship parameter is used to identify the cardinality, or how the records in the views are matched, such as many_to_one. After this overview of Explores and join logic, you can now curate Explores for your business users to analyze and visualize data in your organization’s Looker instance.

## Using LookML to filter Explores

- Recognize and detail the steps and conditions necessary to add a new filter option to an existing Explore using the Looker IDE
- Recognize and identify where in the Looker UI LookML developers can add a new filter option to an Explore
- Recognize and articulate the relationship between the filters you add to an Explore in the Looker IDE and the filters you add to an Explores that data viewers, decision makers, and business analysts use in Looker

To filter an Explore, you need to apply a default WHEREor HAVINGclause to every SQL query that gets generated in that Explore. There are three principal ways to add default filters to an Explore:

- **sql_always_where** and **sql_always_having** - allow you to add filters to an Explore that cannot be modified by business users. This is useful when you have certain rows of data you always want to exclude from the Explore results such as sensitive data or personally identifiable information (PII). The filtering does not display in the user interface, so business users are not informed that the data are being filtered, unless they have permission to look at the generated SQL. 
- **always_filter** - adds a filter to the Explore frontend that is accessible to business users. Users can change the filter operator and specific values, but they cannot remove the filter itself. always_filter has a subparameter to define the dimensions that users must provide values for, such as a value for order status or user country. For example, while the default order status is “Complete”, business users can change this value to say orders with a different status like “Returned”. This filter is helpful for optimizing query performance and cost savings because you ensure that users always filter by specific dimensions and do not request all of the possible data at one time. 
- **conditionally_filter** -  adds a filter to the Explore frontend that is accessible to business users. In this case, users can remove the filter itself if they put a filter on a specific alternative field. conditionally_filterhas a subparameter to define the specific filters as well as a subparameter to define the alternative dimensions that can be
used to filter the data. For example, conditionally_filtercan be used to create a filter that only returns data for the past 1 month, unless a filter is applied to a user ID or state dimension. This filter is helpful when you want to limit the amount of data that a business user requests, but you also want to give them a list of alternative dimensions that they can use to filter the data.

> Remember though, if your Explore filter uses a field from a different view other than the base view, that view will alwaysbe joined in to every Explore query as well, even if the business user doesn’t explicitly select or filter on any dimensions or measures from it. The join to that Explore needs to be there for the filter condition to work.

```
explore: order_items{
    sql_always_where: ${order.items.created_date >= '2012-01-01'} ;;

    sql_always_having: ${order_count} > 10 ;;

    always_filter: [status: "Complete", users.country: "USA"]

    conditionally_filter: {
        filters: [created_date: "1 month"]
        unless: [users.id, users.state]
    }
...
}
```

In summary, there are three principal ways to add default filters to an Explore. sql_always_where and sql_always_having are both used to add filters that cannot be modified or seen by business users. Specifically, sql_always_where is used to apply default filters for dimensions, while sql_always_having is used to apply default filters for measures.

Both always_filter and conditionally_filter are helpful for ensuring that users always filter the data using specific dimensions, so that they do not request all of the possible data at one time. While the filter for always_filter cannot be removed by business users, conditionally_filter allows users to remove the default filter if they choose an alternative dimension from a provided list of options. 

## Understanding symmetric aggregation

- Recognize and define what symmetric aggregation is
- Recognize and articulate how Looker utilizes symmetric aggregation to resolve specific types of data analysis problems

A key concept to understand when working with Explores and join logic is symmetric aggregation. This is a great feature of Looker that ensures accurate aggregation of data for counts, sums, and averages. 

Symmetric aggregation addresses a common problem in data and analytics called the fanout problem.

Imagine you have two tables, customers and orders. The relationship between the tables is one-to-many because a customer can make multiple orders, but each order can only be
made by a single customer.

When considering these tables individually, the count and sum operations produce accurate results. There are 3 total customers, 4 orders, 8 total visits, and $250 in total order spending.

|customer_id|first_name|last_name|visits|
|-|-|-|-|
|1|Amelia|Earheart|2|
|2|Charles|Lindberg|2|
|3|Wilbur|Wright|4|

|order_ir|amount|customer_id|
|-|-|-|
|1|25.00|1|
|2|50.00|1|
|3|75.00|2|
|4|100.00|3|

To join these two tables in an Explore, it is pretty clear that customer_id should be the join key. However, given the one-tomany relationship, you actually produce what is called a fanout when you join them on customer_id. 

|customer_id|first_name|last_name|visits|order_ir|amount|customer_id|
|-|-|-|-|-|-|-|
|1|Amelia|Earheart|2|1|25.00|1|
|1|Amelia|Earheart|2|2|50.00|1|
|2|Charles|Lindberg|2|3|75.00|2|
|3|Wilbur|Wright|4|4|100.00|3|

It introduces a duplicate row for customer_id 1 because Amelia Earhart made more than one order. When performing aggregations on the customers side of the table, you would now get incorrect results. For example, SUM(visits) amounts to 10.

As long as symmetric aggregation is supported by your underlying database, Looker will automatically implement symmetric aggregations when the following two conditions are met. 

- First, every view file in your model must have a primary_keydefined to join it to an Explore. As a best practice, you should strive to define a primary_key in every view regardless of whether it will be joined to an Explore.
- Second, the relationship parameter needs to be specified accurately for every Explore join.

An easy way to test if a primary key is functioning as a unique key is to compare a count of the field you believe to be a primary key against a COUNT(*) on the table. If the two counts return the same number, you have your primary key. If not, you can create a new dimension that concatenates all the columns necessary to make each row unique. 

Another option is to think about the join keys. Is customer_id the primary key? Are the values unique in the first view? What about the other view—is it possible that the same value could appear multiple times there?

> Remember you cannot assign the primary_key: yes parameter to more than one dimension in a view.

So what would happen if you specified the wrong relationship between customers and orders, say, one-to-one instead of one-tomany? Well, in this case, the data on the customer's side would fan out. Remember, you only had 3 customers: Amelia Earhart, Charles Lindbergh, and Wilbur Wright. Their combined visits totaled 8. However, by using a one-to-one relationship instead of one-tomany, the Explore returns 4 customers with a total of 10 visits because Amelia Earhart is counted twice, along with her 2 visits.

If you specify the correct relationship between customers and orders, which is one-to-many, then Looker will automatically apply symmetric aggregation, resulting in the correct outputs of 3 customers and 8 total visits.

So how does COUNT actually work in symmetric aggregation? You might have already been wondering about COUNT(DISTINCT). Since this query executes a one-to-many join, Looker indeed realizes it needs to count the distinct customer_id values rather than a blanket COUNT(*), which would include duplicate customer_id values from the orders side.

Sums and averages are a bit more complex, but function similarly in that distinct records are identified for the calculations using the MD5 hash function. As symmetric aggregation is already implemented by Looker, you do not need to fully learn when and why to use MD5to be a successful LookML developer. 

What Looker is basically doing is generating a unique numeric amount for each primary key value using the MD5 hash function. So the two rows for Amelia Earhart would both get assigned a big_unique_number. Then, to calculate the total true visits, Looker uses basic arithmetic problem to determine whether or not it should count a given number of visits again, something like: SUM(DISTINCT visits + big_unique_number) - SUM(DISTINCT big_unique_number)

In summary, symmetric aggregation is a great feature of Looker that addresses potential fanout problems resulting from data joins. As long as symmetric aggregation is supported by your underlying database, Looker will automatically implement symmetric aggregations when the following two conditions are met. 

First, every view has a primary_key to join it to an Explore, and second, the relationship parameter for every Explore join is accurate. With symmetric aggregation, Looker ensures that your counts, sums, and averages are always accurate for your business users. 

# Working with derived table

- Recognize and define the purpose of a derived table● Recognize and articulate the situations where someone should consider deploying a derived table
- Recognize and articulate how using a derived table can contribute to the larger data analysis process in Looker

Derived tables are a great feature of Looker that allows you create new tables that do not yet exist in a database.

When you work with existing tables in your connected database, you reference the necessary table names in the sql_table_name parameter of the view files.

It is not unusual for existing database tables to be insufficient to assist us in answering more complex questions of our data. Sometimes we need to structure our data in other ways through SQL objects like temporary tables, materialized views, common table expressions (CTEs), and subqueries.

In LookML terms, if you need to produce a CTE or temp table, you need to define a derived table.

The most common use case for derived tables is to overcome structural limitations for patterns that would require a subquery in raw SQL. A nested or multi-step aggregation is a common pattern where we need to do an aggregate of an aggregate. 

### Defining derived tables

Derived tables are either manually written SELECT statements or Looker-generated SELECT statements that produce results that can be queried just like a “real” database table.

Derived tables are integrated in LookML projects as views. You can explore or join those views in the same way as the other views that point to actual database tables.

Derived tables have two types of existence:

- **Ephemeral tables**, which compile at runtime and are generated as CTEs or temp tables.
- **Persistent tables**, or PDTs, which are stored in the underlying database.

The benefit in persisting derived tables is that they are ready to go when business users need them, and therefore reduce query runtimes. The downsides are that they take up storage space in your database (which may correlate to cost), and they are more rigid (they can’t accept dynamic logic). So you may choose to persistent only some of your derived tables, such as the most frequently used ones.

In summary, derived tables are a useful feature for defining new custom tables that do not yet exist in your database. Derived tables are used just like other views in your LookML project and produce results that can be queried just like a real database table. Depending on your use case, derived tables can be ephemeral or written back to the database as a persistent derived table. 

With derived tables, you can create custom tables to aggregate your data in a variety of ways to help you answer business questions.

## Types of derived tables

- Recognize and differentiate between the two types of derived tables 
- Recognize and articulate the situations where someone should consider deploying one type of derived table over the other

In Looker, you can use derived tables to define new custom tables that do not exist in your underlying database. Derived tables are created in LookML projects as views that you can join in an Explore, just like other views that point to actual database tables.

Derived tables also produce results that can be queried just like real database table, and they can be either ephemeral or written back to the database as a persistent derived table.

- Derived tables can be written in SQL, which is an easy option if you’re already comfortable with SELECT statements in SQL. In addition to being easier to learn and understand for SQL users, SQL derived tables have the advantage of being able to leverage complex and custom joins and calculations, as well as the UNION function.
- **Native derived tables (NDT)** - derived tables can also be written entirely in LookML, which we call native derived tables, or NDTs. NDTs embody the essential LookML principle of reusability by allowing you to leverage existing objects in your model, such as dimensions and measures, to define new tables. Because NDTs minimize the number of “hard-coded” database references in your code, they are easier to maintain and allow your model to scale efficiently as your organization’s usage of Looker increases. 

You could create a SQL derived table by writing a SELECT statement, However, what if your LookML model already contains measures for order_item_count and total_revenue? Rather than creating a SQL derived table, you can reuse these existing measures to easily define a new NDT.

This would allow you to avoid hard-coding another reference to the underlying database table, thereby saving you work in the future if and when you need to update those measures. 

In summary, there are two ways to define derived tables in Looker. First, SQL derived tables are easy for SQL users to learn and understand, and can include complex joins and calculations, as well as the UNION function. In contrast to SQL derived tables, native derived tables are expressed entirely in LookML and reuse existing objects in your
model such as dimensions and measures to create new tables. They are often easier to maintain and scale because they minimize the number of “hard-coded” database references in your code. 

Though which option you use will depend on your particular details of your LookML project, both SQL derived and native derived tables are great features in Looker that you can use to create new, custom tables for your business needs. 

## Using SQL derived tables

- Recognize and articulate where in the Looker UI to create a SQL derived table
- Recognize and articulate the specific purpose of a SQL derived table
- Recognize and define the process by which someone would create a SQL derived table

In Looker, you can use SQL derived tables to create new custom tables using manually written SQL queries. 

Begin by ensuring that you are in Development Mode. Then, click Develop on the left side navigation menu to see the develop options.

**SQL Runner** - In Looker, the easiest way to create a SQL derived table is through SQL Runner, which provides an interface for you to write and test SQL queries to your available database connections. 

After confirming that the query returned the desired results, click on the gear icon in the top right corner and choose Add to Project. Select the project name from the dropdown, and give your derived table a descriptive name. Then, click Add. You will be redirected to the Looker IDE to review the newly created view file for your derived table. 

It is a best practice in Looker to keep the view files organized in the views folder of a LookML project. To move the file, simply click on the file in the file browser, and drag the file under the folder named views.

Looker auto-generates a count measure along with the dimensions used in the derived table. Sometimes this auto-generated count measure is not valuable, if you already have a count in another view that provides the same number. So you can either delete the measure, or hide it using the **hidden: yes** parameter.

A final best practice is to ensure that the new view has a primary key. You can add the **primary_key: yes** parameter to a dimension which is the core organizing ID of this
view that provides details about each individual record. 

## Using native derived tables

- Recognize and articulate where in the Looker UI to create a native derived table
- Recognize and articulate the specific purpose of a native derived table
- Recognize and define the process by which someone would create a native derived table

In Looker, you can create custom tables using either SQL derived tables, which depend on manually written SQL queries, or native derived tables, which are written entirely in LookML. Because native derived tables reuse existing LookML objects to define new custom tables, they promote code reusability and reduce hardcoded references to your underlying database tables. The easiest way to create a native derived table in Looker is through an Explore.

To begin, enable Development Mode and then, click Explore. In the Explore, select the dimensions and measures you need for your native derived table. Remember that the Explore will automatically generate a valid, performant SQL query for you. Click the Run button to review the results and click on the gear icon in the top right corner and select Get
LookML. Click on the Derived Table tab, and copy the LookML code to your computer clipboard. In the next steps, you will paste this LookML code into a new view file for this native derived table. 

Return to the Looker home page by clicking Looker on the top leftside of the UI. Then, click Develop to see the options. Click on the project to open the Looker IDE in this project. In Looker, it is a best practice to always create a new view for a new native derived table. To create a new view file in the file browser, click on the plus (+)
icon, and choose Create View. Notice that the view file is automatically created outside of the views folder in the file browser, click on the view file in the file browser
and drag it under views. 

Replace the auto-generated LookML in the view file with your previously copied LookML code. Following another best practice, be sure to change the autogenerated view name to match the view file name.

Notice that Looker makes a suggestion to include the model file but the lines are commented out. It is a best practice to leave the line for the model file commented out.
Otherwise, you risk creating circular dependencies in your model and causing validation errors because model files typically include many other files. 

The new native derived table is now ready for you to create new dimensions and measures, join it to the explore in the model file, and/or finish out the Git workflow to send your changes to production. 

To wrap up this example, let’s review the best practices that you used to create a new derived table. First, you created a new view file for the native derived table, and then moved the new view file to the folder named views. Next, you pasted the copied LookML code into the new view file and replaced the auto-generated view name with the name of the
view file. Last, you left the model file commented out in the view file. Following these best practices, you can use native derived tables to create new custom tables in your organization’s Looker instance. 

## Native derived table parameters

- Recognize and list the two key parameters used in native derived tables
- Recognize and list the additional, optional parameters that developers can use in native derived tables

In Looker, native derived tables allow you to create new custom tables that reuse existing objects in your project, such as dimensions and measures, and are expressed entirely using LookML. To fully understand how native derived tables function, let’s review the parameters in detail.

**explore_source** - A key parameter for native derived tables is explore_source, which points to the Explore in your model that serves as the foundation for the derived table. In other words, it’s the FROM part of your SQL query and specifies any required joins.

**column** - Another key parameter is column, which specifies an output column for the native derived table. In other words, it is a field that is being SELECTed. Sometimes, you will see a fieldparameter inside the curly braces {} for a column. If you have more than one field with the same name throughout the Explore, you can use the field parameter to tell Looker exactly which dimension or measure to use. If your field name is unique throughout the Explore, you can leave the curly braces {} empty. This also means that you can use the field parameter to name new column differently from the underlying field name. 


```
view: order_datails {
    derived_table: {
        explore_source: order_items {
            column: order_id {
                field: order_items.order_id
            }
            column: user_id {}
            column: order_item_count {}
            column: total_revenue {}
        }
    }
}
```

In addition to the key parameters for explore_sourceandcolumns, there are many other helpful parameters for native derived tables.

**filters** - can be used to apply filters to the derived table, similar to a filtered measure. In essence, it adds a WHERE or HAVING clause to the query. 

**bind_filters** - If you need to add a dynamic or templated WHERE or HAVING clause to your derived table logic, you could use bind_filters. This parameter will allow the native derived table to take on the filters that a user applies on a dimension or measure in the Explore query, and makes the filters “trickle down” to the derived table query itself. 

**derived_column** - imagine that you would like to use a field that does not currently exists in the Explore or model. In a native derived table you can use the derived_column parameter to define a new column that does not yet exist in the Explore specified by the explore_source parameter.

**expression_custom_filter** - Traditional filters in Looker only let you specify what are basically key-value pairs and then it forces an AND conjunction between multiple inputs. expression_custom_filter, on the other hand, lets you define nuanced logic with your own choice of AND/OR conjunctions and order of operations.

In summary, the key parameters for native derived tables are **explore_source** and column. explore_sourcepoints to the Explore in your model that serves as the foundation for the derived table and is the basis of the FROM statement in your SQL query. **column** specifies an output column for the native derived table and represents a field that is being SELECTed in your SQL query. In addition, there are other useful parameters for native derived tables, such as **filters** and **derived_columns**, which you can use to apply filters and define new columns that do not yet exist in your Explore.

## Using persistent derived tables

- Recognize and articulate where in the Looker UI to create a persistent derived table
- Recognize and articulate the specific purpose of deploying a persistent derived table
- Recognize and define the process by which someone would create a persistent derived table

In Looker, derived tables can be ephemeral, meaning that Looker builds them at run-time, or they can be persistent, meaning that they are written back to the connected database. The benefit of persistent derived tables, or PDTs, is that they are ready to go when business users need them; while the main downside is that they take up storage space in your database, which may correlate to cost.

We will explore how PDTs are written back to and stored in the connected database in Looker. 

In Looker, ephemeral derived tables build at runtime as temporary tables or common table expressions (CTEs) that are defined in the generated SQL with the following syntax: WITH derived_table_name AS (SELECT column_1 ... and so on.

By contrast, a PDT will run a SQL CREATE statement in the underlying database to create a physical table. Both SQL derived and native derived tables can be saved as PDTs.

When a business user selects a field or filter from a PDT, the generated SQL will join to the PDT, just as it would to a regular table in the database.

Another key point about PDTs is that Looker will build a version of the PDT specifically for your Git branch in Development Mode. After you have deployed your code to  production, or if the PDT already existed in production and you were modifying it, business users querying the PDT in production mode will be pointed to a separate version for production.

We recommend naming the schema for PDTssomething like “X_scratch”, but you could call it anything you want. The important thing is to configure a schema dedicated to Looker 
PDTs in your database. Typically, a database admin would create the schema, and then a Looker admin would specify the schema name in the connection settings of the Looker instance.

Second, although the derived table is named user_order_facts, Looker will auto-generate the name for the PDT, so it can keep track of different versions of the PDT in development or production modes. In the table name, a text string of a long jumble of letters and numbers will be prepended to the derived table name. PDT names always start with this hash, which encodes information such as the database connection and SQL that it uses.

To persist a derived table, you must use at least one of the following parameters in the definition.

**datagroup_trigger** uses a datagroup, or caching policy configured in the model. As a best practice, we recommend using datagroup_trigger if datagroups are already defined in your model.

**sql_trigger_value** uses a pre-written SELECTstatement that returns one value such as the maximum value of a user ID column. Looker sends that SELECT statement to the database repeatedly, and when it discovers the result has changed, it takes this as a cue to rebuild the PDT.

**persist_for** instructs the PDT to be available for a set duration, such as “1 hour” or “4 hours”. There are a few things to consider before choosing this option to persist your derived tables. First, because persist_for does not contain any rebuild logic, the PDT does not get updated at any time within the specified duration. 

In addition, once time is up, the PDT is dropped and is not recreated until the next business user needs it for a query. 

As the primary benefit of PDTs is having data readily available to minimize query runtimes, we recommend that you use persist_for in conjunction with sql_trigger_valueto
ensure that data updates within the duration, or simply use datagroup_trigger or sql_trigger_value on their own.

If you have a use case for it, you can also make SQL derived tables select FROM one or more other derived tables. This would create cascading derived tables due to dependencies between the tables. Given that PDT names always start with a long hash, you can use .SQL_TABLE_NAME (in capital letters) as a substitution operator to refer to the view name. This enables Looker to plug in the physical table name at runtime.

If you persist the cascading derived tables, then it is important to ensure they rebuild in the correct sequence, so the dependent PDTs rebuild with the most recent data. You cannot explicitly control the sequence that Looker users to rebuild PDTs. Now, one way you could try to make all your PDTs build in the right order is to stagger the sql_trigger_value, based on the typical build time of the preceding derived table. As you might imagine, this isn’t foolproof. 

This is another reason why datagroup_trigger is better than sql_trigger_value for applying persistence. If all your cascading PDTs use the same datagroup_trigger, then
Looker will actually be able to detect the dependencies and rebuild the PDTs in the guaranteed correct sequence.

Last, we also recommend that you add indexing to your PDTs. Indexing is like a card catalog in a library, where you could look up the location of a book to quickly find it among the shelves. Similarly, indexes help databases process queries more quickly. Looker accepts the indexing parameters for most database dialects. We suggest discussing indexing of PDTs with a data engineer or database administrator at your company to determine the best option for your use case.

In summary, after PDTs are written back to your databases, they are stored as physical tables that be queried and joined just like any other table in your database. Looker builds a separate version of the PDT in development and production modes to ensure that you can create and test PDTs without impacting the production environment until you are ready to merge your updates. Be sure to create a schema specifically for Looker PDTs. Within this schema, Looker auto-generates the name for the PDT, so it can keep track of different versions and encode information such as the database connection and SQL that it uses.

## Caching and datagroups

- Recognize and define both caching and datagroups incontext 
- Recognize and articulate the situations where someone should consider deploying caching and datagroups to improve query performance
- Recognize and articulate how using caching and datagroups can potentially benefit the larger data analysis process in Looker

In Looker, caching is a useful feature that LookML developers can use to reduce database load and optimize query performance. Caching leverages the saved results from previously executed queries, so that the same query does not need to be run on the database each time. 

The overall caching process in Looker is straightforward andbegins with a query. As users are exploring and analyzing data, Looker generates SQL queries and checks whether there are valid cached results for each query.  

If there are valid cached results for a query, Looker will avoid requesting the same data again from the database, and instead, simply send those cached results back to the user. If there are no valid cached results for that query, Looker sends the query to the connected database. These new SQL results are then cached and stored in an
encrypted file on the Looker instance. This file can then be used by Looker, if and when the same query is run again.

Now, to help ensure that cached results remain valid and up-todate, LookML developers can set up datagroups, or caching policies, to manage the frequency and conditions for caching on a Looker instance. For example, a datagroup can be created to ensure that all cached results are updated at least once an hour, or when a new ID is added for a key field such as user ID or order ID. 

The datagroups are then used by Looker to check whether cached results are still valid. If the cached results are no longer valid per the datagroups, Looker will send the query to the database to obtain new results. 

In Looker, datagroups can be defined both to establish cachingpolicies and rules for entire models, individual Explores, or specific PDTs in your LookML projects, and to  ensure a refreshed cache. The number and types of datagroups you would need to create depends on how often your data is updated and should take into account your organization’s data extraction, transformation, and loading (or ETL) processes and business requirements. 

To define a new datagroup using LookML, you must provide a unique name and two parameters: max_cache_age and sql_trigger. 

```
datagroup: daily_etl {
    max_cache_age: "24 hours"
    sql_trigger: SELECT max(id) FROM my_tablename
}
```

**max_cache_age** - specifies the maximum number of hours to keep a cached result, such as 24 hours. 

**sql_trigger** - is used to write a SELECTstatement that can tell Looker whether the results have changed. The sql_trigger should be written to return only one value, such as the maximum ID value in a table. Looker will send this statement to the connected database on a regular frequency. Once it finds that the value has changed, Looker takes that as a cue to refresh the cache.

Of course, while only one of these parameters is required, we do recommend as a Looker best practice using both to achieve the desired caching results. For example, if no change is detected by the sql_trigger check, that could mean something went wrong with the database ETL process or the sql_triggeritself. By including a max_cache_age, the cache would still get refreshed regardless after a set duration.

The frequency of the sql_trigger’s pinging of the database is defined in the connection settings by your Looker administrator. The frequency is determined by a cron string in the connection’s PDT And Datagroup Maintenance Schedule field. By default, it is every 5 minutes. The frequency of the sql_triggercheck should match the approximate frequency of the data updates. For example, every 5 minutes is too frequent if your data warehouse is only updating every few hours or once per day.

In addition, companies using certain database dialects may want to let the database “hibernate” outside of work hours to save money, so they would not want Looker waking up the database with sql_trigger checks. 

Be aware though that in Looker, defining a datagroup by itself doesn’t do anything. It is a two-step process. After defining the datagroup, you need to apply the datagroup to a LookML object. 

you can use the persist_with parameter to apply a datagroup at the model level. When you do this, Looker will apply the same caching rules to all Explores within this model. In
fact, whenever you create a new LookML project by having Looker generate the model from the database schema, Looker will automatically create a default datagroup in the model file that you can customize as needed. 

You can also choose to apply a caching policy on an individual Explore, which would override whatever is set at the model level. 

For example, to apply a datagroup to specific Explore, use the persist_with parameter within that Explore’s definition, rather than at the model level. To apply a datagroup to a specific set of Explores but not all Explores in a model, use the persist_withparameter in each Explore’s definition and specify the same datagroup name. Since Explores are the foundation for all content in Looker, the same caching logic would carry over to Looks and dashboards created from the Explore.

You can also use datagroups to tell Looker when to rebuild a persistent derived table (or PDT). 

To do this, simply specify the datagroup name in the datagroup_trigger parameter of the PDT. While there are a few different options for persisting derived tables in Looker, using the datagroup_trigger parameter is the recommended best practice to ensure that the data remain current. 

Additionally, schedules for Looks and dashboards can also be run on datagroups. You can instruct Looker to run a Look or dashboard automatically upon expiration of a caching policy, so new data is retrieved and “pre-cached” for any business users who need it.

> Please remember though if your database connection is configured in Looker to use dynamic usernames such as OAuth for BigQuery, then you cannot use datagroups for models using that connection. Instead, use a persist_for parameter to cache Explore queries for a fixed amount of time. In addition, remember that when using OAuth for BigQuery, persistent derived tables are not supported. 

In summary, every time that a user runs a query, Looker checks to see if that query has been run before. If it has not been run before, Looker runs the query on the
database, and then caches the results for future use. If the query has been run before, Looker then checks the caching policies to evaluate whether the results should still be considered valid. If the cached results are still valid, Looker returns the cached results to the business user. If the same query has been run before, but the results are no
longer valid per the caching policies, then Looker sends the query to the database to get new results. It then caches the new results for future use.

# Fostering a great user experience

## Custom homepages

As a Looker administrator, you have many types of responsibilities that directly impact your end users, from the ongoing performance optimization of the platform, to managing content access and permissions.

One additional responsibility you might not have considered is that of the experience your end users have upon landing into the Looker platform after login. What content is displayed to them? How is it organized? Many organizations choose to use Looker’s default homepage, but you are not bound to that. You can design and create different homepage experiences for different communities of users within your organization.

The easier and more organized content is offered and discoverable within the Looker platform, the better experience your end users will have. Specifically, the Looker content they care about most, available to them in as lightweight a way as possible.

We, all of us, also interpret data differently and work differently as a result. We at Looker fully acknowledge this and have provided the ability for Looker administrators like you to craft different custom homepage experiences for different teams and individuals within your organization.

Ultimately, though, what does all this mean? Yes, empowering your end users with better content discovery truly can empower the entire organization, but it also directly impacts Looker adoption and user retention at your organization.

## Creating a custom Looker homepage

As a Looker administrator, you have a vested interest in fostering the best possible experience for your users. As previously discussed, one way to actively promote that great end user experience is to provide them with a custom Looker homepage. We’re not saying that you need to create a custom homepage for every individual or team in every situation.

In the admin panel of the Looker user interface, you will see the “Homepage” menu option. After clicking into that, you’ll see that you are presented with two ways of assigning homepage experiences to your end users. If you want to assign a custom (or default) homepage experience to your entire organization, you can toggle between them.

If your end users or teams already actively utilize a Looker board, you can define for them that board as their custom homepage experience.

If your end users or teams require something more tailored to their specific needs or responsibilities, you can write a Markdown file using the Looker integrated development environment (IDE). Using Markdown, you can very logically organize and curate Looker content for your users or teams. The power of Markdown here is that you can make this as simple or exactingly specific as your users’ needs demand. Once you create your Markdown document, you can simply declare the path to it in the Homepage section of the Admin panel.

If you want to define different experiences for different teams and individuals, you can edit the landing_page user attributes to route them to their different homepage experiences. As a Looker administrator, you have both full and entirely granular control over the experience of your end users. You would simply browse to the User Attributes page from the Users section of the Admin panel, and then configure the landing_page attribute for as many users or groups as you see fit.



