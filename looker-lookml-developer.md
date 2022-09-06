# Looker LookML Developer

## Introducing to Looker and LookML

- Recognize and articulate the value proposition of the Looker platform
- Recognize and articulate the value proposition for modeling data using the LookML modeling language

Looker is a Business Intelligence (BI) software and big data analytics platform that helps business users to explore, analyze and share real-time data analytics easily.

As a browser-based, Software as a Service (SaaS) platform, Looker connects directly to SQL databases.

- Other SaaS applications such as Salesforce, Mailchimp, and Zendesk.
- Heavy read-write operations in transactional databases such as Oracle, IBM Db2, and Microsoft SQL Server.
- Business planning tools such as SAP, NetSuite, and Oracle.
- And web analytics products such as Google Analytics or Adobe Analytics.
- Looker is multi-cloud and supports over 65 database dialects.

### Architecture

#### Looker Agile Modeling Layer

One major benefit of Looker is its agile modeling layer, which can save data teams and business analysts time that would otherwise be spent manually writing and editing SQL queries. Looker’s agile modeling layer allows developers to define, through Looker Modeling Language or LookML, how the database is structured and how the tables and columns relate to each other. 

A useful way to think about LookML is that it is an abstraction layer for SQL that developers use to tell Looker what data to use from the connected database and how it should interpret that data. 

As users explore and analyze the data, Looker uses the defined LookML models to automatically generate SQL SELECTqueries to send to the database and return the appropriate results.

#### Looker Data Governance

Another benefit of Looker is data governance, which means that you can define a single source of truth for data that everyone in the organization can understand and trust.

In Looker, you can enforce various types of data security and governance through the Looker User Interface (UI), such as assigning specific user roles, as well as through LookML, such as providing access to specific fields or rows of data. 

#### Looker Data Democratization

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


