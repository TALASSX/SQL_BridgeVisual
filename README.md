Power BI SQL Writeback Visual
This repository contains the necessary files for a pre-built Power BI custom visual that enables real-time data writeback to a SQL database. This visual allows end-users to perform full CRUD (Create, Read, Update, Delete) operations and bulk data imports directly from a Power BI report.

1. Visual Overview
The visual operates on a two-part architecture:

Read Operations (Direct Query): The visual retrieves data directly from your SQL database using a standard Power BI Direct Query connection.

Write Operations (Middleware): All write actions (insert, update, delete) are handled by a separate middleware server. This server, which you must have deployed and configured, acts as a secure proxy. This design ensures that sensitive database credentials are never stored within the Power BI report file itself.

2. Prerequisites
To use this visual, you must have the following prepared:

Power BI Desktop: The application used to configure and view the report.

Deployed Middleware Server: A pre-existing middleware server that is configured to connect to your SQL database. You will need the URL of this server.

SQL Database Table: A SQL database with a table that contains the data you want to manage with the visual.

Firewall Configuration: The middleware and sql server server's firewall must be configured to allow it to connect to your database.

The .pbiviz File: The custom visual file provided in this package.

3. Installation and Configuration
Follow these steps to set up the visual in your Power BI report:

Import the Visual: In Power BI Desktop, navigate to the Visualizations pane. Click the "..." button and select Import a visual from a file. Choose the SQL_BridgeVisual.1.0.0.0.pbiviz file.

Add Data: Drag the visual onto your report canvas. From the Fields pane, drag all the columns from your data model's table into the visual's Table Columns field well(note- first column should be your Primary Key).

Configure the Connection: With the visual selected, go to the Format pane (the paint roller icon). Find and expand the Database Configuration section. Fill in the following details:

Server: Your SQL Server instance name.

Database: The name of the database.

Username / Password: The credentials for the database account.

Middleware URL: The public URL of your deployed middleware server.

Schema / Table Name: The database schema and the exact name of the table for writeback.

4. Usage Guide
Once configured, the visual will display your data in a dynamic table.

Insert a Record: Click the Insert button. Fill out the form that appears and click Submit.

Update a Record: Select a row by clicking on it, then click the Update button. A pre-filled form will appear for you to edit.

Delete a Record: Select a row, click the Delete button, and confirm the action.

Import Data (Bulk Insert): Click the Upload CSV button. Select a CSV file from your computer. The visual will show a preview before you confirm the import.

After any successful operation, the visual will automatically refresh your page to display the updated data.

5. Included Files
SQL_BridgeVisual.1.0.0.0.pbiviz: The compiled Power BI custom visual file.

User Guide SQL Writeback.docx: A detailed user guide with step-by-step instructions.
