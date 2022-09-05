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

## Data analysis building blocks

### Dimensions in Looker

At the conclusion of this lesson, you will be able to:

- Recognize and define the purpose of a dimension in Looker
- Recognize and articulate where in the Looker UI end users work with dimensions
- Recognize and define to what asset a dimension corresponds in your database
- Recognize and articulate how dimensions contribute to the larger data analysis process in Looker

Dimensions are attributes or characteristics of your data. Specifically, each column in a database table is a dimension in Looker.

When you select a dimension in Looker, only the unique possible values are displayed. Be aware that selecting multiple dimensions may result in more rows or different groupings than you may initially expect.

In summary, dimensions help you to identify and select data attributes that you need to answer your questions in Looker. Each column in a database table is a dimension in Looker, and you can combine dimensions to return all the unique combinations of the values.

### Measures in Looker

At the conclusion of this lesson, you will be able to:

- Recognize and define the purpose of a measure in Looker
- Recognize and articulate where in the Looker UI end users work with measures
- Recognize and define to what SQL functions a measure can correspond
- Recognize and articulate how measures contribute to the larger data analysis process in Looker

Measures are calculations performed across multiple rows of data. As such, measures are aggregates of data attributes, or dimensions.

In summary, as highlighted in these examples, measures are useful for aggregating dimensions (or data attributes), so that you can easily calculate values such as count, sum, or even averages across your data.

Looker tries to guess the right type of visualization based on the data in your results set.

### Using dimensions and measures

At the conclusion of this lesson, you will be able to:

- Recognize the relationship between dimensions and measures
- Recognize and articulate how the relationship between dimensions and measures contributes to the larger data analysis process in Looker.

In real-life analytics, you often need to combine dimensions and measures, in order to answer your data questions.

By combining the necessary dimensions and measures, you can answer more complex questions by fully leveraging datasets that have many available attributes and aggregations.

### Filtering dimensions

- Recognize and define the process of filtering by a dimension in Looker
- Recognize and articulate where in the Looker UI end users can filter dimensions
- Recognize and articulate how filtering by dimensions can contribute to the larger data analysis process in Looker

In Looker, filters are ways to reduce or narrow down the results returned based on specific criteria. In this way, filters allow you to hone in on a subset of your data based on desired characteristics.

You can use dimension filters to select only the data you want to see in your results, without affecting the underlying data tables.

### Filtering measures

- Recognize and define the process of filtering by a measure in Looker
- Recognize and articulate where in the Looker UI end users can filter measures
- Recognize and articulate how filtering by measures can contribute to the larger data analysis process in Looker

In Looker, you can filter on both dimensions and measures to select only the data you want to see or include in your results. In either case, the underlying data is not affected, and Looker knows which data to include or exclude based on the filter.

With measure filters, Looker first gets all the possible rows and calculates all the potential aggregations. Then, Looker discards the undesired results at the end, before returning the results.

If a dimension is used as a filter, then Looker will apply that filter first and then aggregate data based on the measure that has been selected.

When you use a dimension filter, Looker will exclude the rows that do not meet the criteria at the very beginning of the analysis. 

When you use a measure filter, Looker first calculates all the potential aggregations and then excludes the results that do not meet the desired criteria at the end of the analysis, before returning the results.

## Working with Looker content

### Filtering Looks

- Recognize and define the process of filtering within a Look in Looker
- Recognize and articulate where in the Looker UI end users can filter within Looks
- Recognize and articulate how filtering within a Look can contribute to the larger data analysis process in Looker

Throughout your data analysis and visualization workflows in Looker, you will likely work with Looks that you have already made or that were made by others.

One of the most common and powerful ways to modify an existing Look is to apply filters to it, so that users can limit the results returned based on specified criteria.

To apply filters to a Look, you need to first enter Edit mode in the Look by clicking on the Edit button in the top right of the screen.

Now that you are in edit mode, you can add filters in the same way that you apply filters in an Explore, by using the field picker in the left-side panel to choose filters from dimensions and measures.

All that is left to do is to save the changes to your Look by clicking the Save button in the top right corner of the screen, in the blue bar.

### Introducing Looker dashboards

- Recognize and define the components that comprise a dashboard in Looker
- Recognize and define the purpose of a dashboard in Looker
- Recognize and articulate where in the Looker UI end users can work with dashboards
- Recognize and articulate how dashboards can contribute to the larger data analysis process in Looker

You can create new dashboards by saving visualizations from an Explore or an existing Look to a new dashboard. In an Explore or Look, simply click on the settings gear on the top right, and select Save to a Dashboard. Then, select the folder where you want to create your new dashboard.

Editing dashboards to add new content or revise the existing layout is also very easy. Start by clicking on the three vertical dots icon for Dashboard Actions at the top right of the page, and select Edit Dashboard.

In edit mode, you’ll see options to add tiles and filters to the dashboard as well as modify its settings to configure how the dashboard runs and refreshes. To add new content to a dashboard, you can click on Add Tile to add a new visualization or text tile. Selecting a new visualization tile will display a new Explore window for you to build the visualization, which you can then save to the dashboard. Text tiles can be useful as section dividers or commentary for your dashboard viewers.

Once in edit mode, you can also rearrange the tiles by clicking on the top left corner of a tile and dragging it around to the desired location. You can also resize a tile by clicking on the bottom right corner and dragging to the desired size.

### Filtering dashboards

- Recognize and define the process of filtering within a dashboard in Looker
- Recognize and articulate where in the Looker UI end users can filter within dashboards
- Recognize and articulate how filtering within a dashboard can contribute to the larger data analysis process in Looker

In Looker, dashboard filters, sometimes called global dashboard filters, behave similarly to dimension and measure filters in that they allow users to limit the results based on a specified criteria.

To add a new filter to a dashboard, first make sure you are in edit mode on the dashboard.

Start by clicking on the three vertical dots icon for Dashboard Actions at the top right of the page, and select Edit Dashboard. Then, click on Filters in the top menu bar, followed by Add Filter.

Next, you need to select the dimension and/or measure that you want to use as the filter. You need to give your filter a name or title, choose how the user interacts with the filter, determine the layout and whether they can select single or multiple values, and if desired, configure a default value for the filter.

You can also expand the Additional options to require a filter value or select other filters to be updated when this filter changes. This last option is useful if you want what we call a “faceted filter.” A common example would be if you have one filter for State and one for City, and you want to make sure that when someone selects a state the list of available cities updates to offer only the cities in the selected state.

On the Tiles To Update tab, you can identify the tiles that you want to update with the new filter. Looker even starts you off with some suggested tiles.

An important thing to keep in mind about dashboards is that you can add tiles from different Explores—in fact, that flexibility is what makes them so powerful and valuable. So sometimes, you may find that only some, but not all, of the tiles get automatically identified to be populated with your new filter because the other tiles aren’t based on the same Explore.

Sometimes you might not want filters to apply to all tiles. Again, it’s a question of what you’re trying to achieve with the filter; it’s more about design than any scientific rule. For example, imagine that you have a tile that shows the number of orders year over year. If someone else were to change the Created Month filter value to just the past 6 months, then the tile would only display one big bar for this year.

Any time you have a tile like this that is supposed to show data for all time, all regions, all something—you might want to head back to the Tiles To Update tab and select the Field to Filter option to “Do not filter”.

Finally, when you are adding filters to your dashboard, be sure to click Save to save your changes!

### Curating Looker content with boards

- Recognize and define what a board is in Looker
- Recognize and articulate where in the Looker UI end users can work with boards
- Recognize and define the process of creating a board in Looker
- Recognize and define the process for pinning Looks and dashboards to a board in Looker

Boards are a great way to centralize relevant content that lives in different folders within your organization’s Looker instance. The great thing about boards is that they simply link to a content item such as a Look or dashboard, which remains in its original location. So boards do not store the actual content, and the original
content remains unaffected.

With boards, you also don’t have to worry about permissions or data privacy because users still need access to the folder containing the item, in order to access that content from a board.

For example, the Favorites menu shows all your own bookmarks, but creating a board allows you to share those bookmarks with other users and teams. Any Looks and dashboards added to the board will still live in their original folders; the board merely links to them and serves as a centralized page to easily find the content.

In addition to creating your own boards, you can also browse all boards that you have access to within your organization. On the Looker home page, click on the plus sign (+) icon next to Boards in the left-side navigation panel, and select Browse all boards.

You can add Looks and dashboards by clicking on the blue plus sign (+) next to Pin a dashboard or Look. A window will open for you to navigate and select the content that you want to add.

Looker also provides the ability to group content by adding new sections, and you can write a description for the entire board itself, as well as for each individual section, to aid others in using the board efficiently.

Looker also makes it easy to pin a Look or dashboard to a board when you are viewing the content in its original location. For example, from a Look, click on the gear menu at the top right of the screen, and choose Pin to a board. You can follow a similar process to pin a dashboard when viewing it in its original location.

Looker also makes it easy to explicitly share access to your board with others. Simply click on the share icon at the top right of the page, and select the users that you want to access the board as well as their level of access such as view or edit. Remember, boards can be for your own benefit, for people you invite, or even for your entire team or
organization.

Don’t worry, though. Even if a user is given access to the board, they cannot view a particular content item on a board if they don’t already have access to see it.

In the browse window, you will be shown every board to which you have access within your organization’s Looker instance. Remember, though, while you may have access to a board, you may not have access to all or any of the content curated on that board. To get access to the underlying content, you can reach out to your Looker administrator.

### Pivoting data in Looker

- Recognize and define the process of pivoting data in Looker
- Recognize and articulate where in the Looker UI end users can pivot their data
- Recognize and articulate the situations where someone should consider pivoting data in Looker
- Recognize and articulate how pivoting data can contribute to the larger data analysis process in Looker

In Looker, pivots allow you to turn a selected dimension into several columns, which creates a matrix of your data similar to a pivot table in spreadsheet software. This is very useful for analyzing metrics by different groupings of your data, such as getting counts for each category or label in your dataset.

When you pivot on a dimension, each unique possible value of that dimension becomes its own column header. Any measures are then repeated under each column header.

With pivots, Looker allows you to regroup your data, so that you can easily compare results by different groupings and identify potential gaps, all while leaving your underlying data unaffected.

## Introducing table calculations

- Recognize and define the purpose of a table calculation
- Recognize and articulate the situations where someone should consider writing a new table calculation in Looker
- Recognize and articulate how writing table calculations can contribute to the larger data analysis process in Looker

In Looker, table calculations provide you with the ability to define new metrics instantaneously using custom formulas.

Table calculations are used to define what we call “on-the-fly metrics” because they run on your query results, instead of your whole database.

You’ll need to start by generating results with at least one dimension or measure, and then you can incorporate these fields into spreadsheet software-like formulas to calculate a new metric.

With table calculations, you can also set up a custom field that isn’t included in the set of dimensions and measures provided by your LookML developers.

Table calculations are really cool and convenient. However, because they run after the query has been set up and are written on the fly, they can introduce differences across an organization, and they need to be recreated manually if they are not saved to a Look or dashboard.

So, we recommend using table calculations for a couple of specific use cases.

- The first is to prototype a field or query, like if you want to validate whether it’s useful enough to reuse. Similarly, if you need to answer a one-off question, then a table calculation is useful. If you find yourself needing the same logic repeatedly, you should work with your LookML developer team to have that logic added to the data model as dimensions or measures that everybody can use.
- Another scenario that might call for a table calculation is if you need to create something based purely on the results set and not on the overall data. A specific example would be if you want to create a specific kind of visualization, like one not available in your current Looker version or for which you don’t have the right types of fields in your data model. In this case, you can use a table calculation to translate your data or visualization into the form you want.

Since table calculations only operate on the results of your Explore query, you first need to bring in one or more dimensions or measures by selecting the fields you need to calculate the desired metric and then click Run.

After you select the dimensions and measures and run the initial results, you can now create a new table calculation from the results. Next to Custom Fields, click the Add button, and select Table Calculation. A new popover window will appear in which to enter your formula.

Now, one thing to be aware of here is that because administrators must enable this feature for end users, you might not have the Custom Fields view in the Explore of your organization’s Looker instance, even if you do have permission to use table calculations. In that case, you would see a Calculations button at the top of the data table.

Assuming Custom Fields are available to you, in the table calculation popover, you will need to select a calculation type, or leave the selected option for Custom expression to write ad hoc expressions. Next, give your new table calculation a name. This name will show up as the column header and in the legend of the visualization.

If using a custom expression for the table calculation, enter the formula you’d like to apply. You can get the absolute value of a number, add time intervals to a date, concatenate multiple values, write if-conditions, and so on.

An important thing for people very familiar with spreadsheet software to know is that with Looker table calculations, you do not start the formula with an equals sign. That might feel a bit weird, but you’ll get used to it.

Next, specify the format of the results if you’d like: decimals, percent, and so on.

Finally, click Save to save your table calculation.

You will now see table calculations appear in your data table in green. The values will show up right away since you have already run your query with the dimensions and measures.

If you don’t want a specific field or table calculation in your visualization, you can click on the gear icon in the column header and select Hide from Visualization. An icon of an eye with a line crossing over it will appear to indicate that the column is hidden.

In addition to writing custom expressions for table calculations, you can choose from some predefined options such as calculating the percent of column total, percent change from a previous row, running totals, and more. With options for both predefined and custom expressions, Looker gives you the power to customize your visualizations and reports as needed.

In summary, table calculations allow you to instantaneously create new metrics and fields, without needing to wait for a LookML developer to create them for you.

Enjoy using table calculations. Just remember that since they run after the query has been set up and are written on the fly, they can introduce differences across an organization, and they need to be recreated manually if they are not saved to a Look or dashboard. 

For these reasons, table calculations are most useful for prototyping new metrics, answering one-off questions, or creating visualizations based purely on query results.

### Types of table calculations

- Recognize and detail the various types of table calculations
- Recognize and articulate the purpose of each type of table calculation

With table calculations, you can prototype new metrics or create one-off visualizations from your query results, without having to wait for a LookML developer to modify the options available in a particular Explore. There are four basic types of table calculations in Looker: string, mathematical, logical, and date & time.

- String functions operate on query results that are text. For example, they can be used to capitalize letters and words, extract parts of a phrase, check to see if a word or letter is in a phrase, or replace elements of a word or phrase.
- With mathematical functions in Looker, you can apply any kind of math on numeric values, such as arithmetic, averages, sums—even running totals and standard deviations.
- With logical functions, you can check one or more conditions and execute different paths of logic, depending on the value.
- Finally, date and time functions operate on datetime results and allow you to extract time periods and calculate date differences and additions. You can also get the current date, time, or date and time, and create arbitrary date fields as needed.

