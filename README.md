# google-looker-certification-guide

1. Looker Platform
2. Data analysis building blocks
3. Working with Looker content
4. Customizing Explores
5. Creating new Looker content
6. Sharing Looker data with others

# Looker Platform

- What is Looker?
- The Looker platform

## What is Looker?

At the conclusion of this lesson, you will be able to:

- Recognize and articulate at a high level the value proposition of the Looker platform
- Recognize and articulate Looker’s role in the data analysis process

Looker can help you:

- See the data your company collects.
- Answer questions as you have them.
- Stay up date with the status of your business.
- Use data for daily decisions, instead of waiting for reports.

To consider how Looker can support your data workflows, let’s examine the overall data analysis
process and the role of Looker in this process.

When working with data, it’s important to have clear objectives.

Data analysis process:

1. **Define questions**: Identify what questions need to be answered using your data.
2. **Identify required data**: Determine the specific dimensions and measures you will need to answer those questions.
3. **Analyze data**: Explore the dimension and/or measure relationships via tables and visualizations.
    - This exploration of your data should empower you to take some kind of action or make some kind of decision with regard to your work.
5. **Interpret results**: Glean actionable insights from your analyzed data.

Looker can support you throughout this process. For example, you can explore your data in Looker to help you define questions and identify necessary datasets.

Then, you can use Looker to analyze and visualize data to answer your questions.

Last, you can share visualizations and dashboards with your stakeholders to facilitate discussion on the results and identify next steps.

Independent of the datasets used, this data analysis process is transferable and can provide a useful framework for thinking about how Looker can be integrated into your existing workflows.

## The Looker platform

At the conclusion of this lesson, you will be able to:

- Recognize and detail the primary components of the Looker user interface.
- Recognize and articulate the audience and purpose of the primary components of the Looker user interface.

Looker is a browser-based cloud application, you access it by opening an internet browser.

When you first log in to the Looker platform, your home page may vary depending on what your company’s Looker administrator has configured.

**Folders** in Looker are where content lives, just as files in your computer or Google Drive are stored in folders.

**Looks** are standalone reports or visualizations, while dashboards contain more than one visualization.

The left-side panel provides the content navigation options for users that have been added to the Looker instance as data viewers, which are users who need to find existing  information quickly and easily. 

> Data viewers do not create their own reports and visualizations.

- **Explore menu** - If you have been added as a data explorer to a Looker instance, you will also see the Explore tab in the left panel of the Looker UI.

As a data explorer, you use Explores to ask questions of your data and create visualizations and reports that can be shared with others such as data viewers.

Explores are curated by Looker developers in a proprietary templating language called **LookML**. The Explores that you have been given access to will be listed under this Explore tab.

- **Develop menu** is used by LookML developers to curate the Explores that are accessible to data explorers via the Explore tab.

Within the Develop environment, developers can specify which fields are available in each Explore, how each field appears, and the logic or behavior for each field. Developers can use the toggle button at the bottom left-side of the UI to enter Development Mode to make and test changes to LookML code before sending the changes to production.

> At your organization, you may not see a Develop menu if that is not part of your role.

- **Admin menu** Looker administrators use the Admin menu to configure the users, permissions, and other settings for the Looker instance such as database connections.

> At your organization, you may not see an Admin menu if that is not part of your role.

- **Recently viewed** - you can access your recent Looker content browsing history in Recently viewed. This might be useful if you need to access a report from a day or two ago.

- **Favorites** - When you do find something that you want to save for future reference, you can add it as a favorite. This section will contain all of your
bookmarked dashboards and Looks.

- **Boards** serve as a useful way of organizing content, such as saving multiple Looks and dashboards onto one board that you can share with others.

- **Folders** - if your Looker administrator has installed any tools or Blocks (which are pre-built data models from the Looker Marketplace), they would also show up in this left-side panel.
    - **My folder** - Each user has a personal folder with their name on it; in the current view, it is labeled as My folder. For you as a Looker user, this is your own scratch space for works in progress, as well as a storage space for content that is only meaningful to you or your role.
    - **All folders** - you can go to the People folder under All folders to see other users’ personal folders.

From the top-right, you’ll see four icons:

1. **Magnifying glass** allows you to search across the Looker instance by keyword and also links you back to Looker Connect for learning assistance.
2. **Looker Marketplace** is where you can find applications and tools to get more out of your data.
3. **Help icon** provides links to chat support, docs, a user guide, and more.
4. **User** icon is where you’ll find access to information associated with your Looker account.
5. **Settings icon** if you have admin access, a fifth gear icon will appear between the Looker Marketplace and help icons that allows access to the admin settings page.

### Browse page sections

- **Folders** section contain Looks and dashboards for specific groups of people. You can copy, move, or save Looks and dashboards to a folder. Folders can also contain sub-folders.
- **Dashboards** section shows various pieces of data in one location. Each section of a dashboard is referred to as a single visualization or tile.
- **Looks** a Look is a single report.

Dashboards in business intelligence show you various pieces of information about some overall topic or domain. In Looker, you can click on a visualization to “drill down", meaning you can see a more detailed breakdown of the data. 

If you have permission to access the underlying data, you will usually find an option to **Explore** or **Explore from Here** to drill down into additional information. Clicking on this option takes you out of the dashboard and into a separate interface called the **Explore**. From this point on, you can work with the underlying data through
the Explore without affecting the dashboard that you were just viewing. Explore is a report-builder interface as well as a portal to ask questions of your data.

To the left of the screen is the field picker. Fields are bundled in these expand-collapse menus called views. Each view is a related concept.

Each view has dimensions at the top, which are attributes of the data, and measures at the bottom, which are aggregations of the data attributes. Use fields to filter data. After adding, removing, or modifying fields in the Explore, you always need to click the Run button in the top right corner.

Now, from here, you could click on the gear icon to:

- save this as a Look for future reuse.
- save it to a dashboard, if you plan to gather more related, but separate, information.
- download it to your computer in a format such as CSV or spreadsheet.
- or send it to a colleague for review and next steps.

## Organizing Looker content

At the conclusion of this lesson, you will be able to:

- Recognize and interpret Looker’s hierarchical folder structure for content
- Recognize and detail the various destinations where content can reside within the Looker
platform

A common challenge that organizations face is that people struggle to find relevant content that already exists, so they make their own, causing duplicates and confusion.

To help you address this challenge, Looker provides many ways to organize content to make it more discoverable to others at your organization, including the ability to create and share folders within your Looker instance.


### Shared folder

Depending on the settings configured by your Looker admin, it is common for the Shared folders page to be set as the home page for users.

All shared folders that are accessible to you will appear at the top of the Shared folders page under the header called Folders.

If you have been granted the permission to create new folders in your Looker instance, you can create a new shared folder by clicking on the New button in the top right-hand corner next to the gear menu icon. The new shared folder will be visible to all users within your Looker instance that can access items
within Shared folders.

The goal of the shared folder is to make the content stored there as easy to find and use as possible. Be sure to take a moment to review the existing Shared Folders structure as you decide when and where to create new folders and their appropriate names.

### My folder

In Looker, all users are provided with their own personal folder as a scratch location to work with content. While your personal folder is intended to be your own space for works in progress, and other items that you may not need to share, other users within a Looker instance can be granted access to your personal folder, if needed, by Looker administrators.

Just like in the shared folders, you can click on New within My folder to create a new folder, if you have the permission to do so.

### All folders 

All folders is useful to easily and quickly see all the folders that you have access to within your Looker instance. The All folders page provides links to Shared folders as well as other users’ personal folders within the People folder.

