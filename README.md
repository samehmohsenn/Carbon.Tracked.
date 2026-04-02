### Carbon. Tracked. Created with ReactJS, Vite, ExpressJS and a mongoDB database.

Carbon. Tracked. is a MERN stack project centered around enterprises' concern towards achieving a lower carbon footprint, while still continuing to provide the essence of their business.

This project includes all of the functionality needed to provide all the operations needed by the web app, read this document to prepare to run this locally.

# Preview: 

## SignUp / Login / Logout: 
![signup-login-logout preview](https://github.com/user-attachments/assets/04af0138-14df-4302-866d-48f336ccc4b5)

User can signup providing the Company Name, a unique username, the industry it inhabits and a password.

User cannot access any pages without a token (without being logged in).

## Data Entry: 
![data-entry preview](https://github.com/user-attachments/assets/312ccbba-26f2-4f0a-b217-1d62491a5d28)

For each month, user can input data for the categories responsible for CO2e and their values, they can dynamically add more or remove categories as applicable to their case.

Users cannot add more than one entry for the same month, to prevent double entries and confusion, user must first delete the old entry from the reports.

They can also see the current categories available in the backend database on the right, providing their name and their unit, so the user knows exactly what kind of data to input.

## Reports Visualization / Viewing / Search / Deletion: 
![reports visualization-viewing-deleting-searching](https://github.com/user-attachments/assets/edb390b4-a318-4ea8-86c1-7a441ba374d5)

A visualization of the emission reports is shown on a bar chart, depicting each month's total emissions, each month's bar is split into calculated sections with different colors to reflect the amount of emissions caused by each category

For each month entry, a corresponding report is shown that shows the total emissions during that month, the highest emitter, a table showing each category's CO2e and a suggestions area, which provides suggestions for how to decrease their emissions, each emission category's suggestions is shown if it passes the threshold defined in the backend's database.

A delete button is present at the bottom of each report to delete the report and its corresponding data entry, the user can then reenter the month's data.

A search box on the page can filter the reports shown and visualized on the page, based on month, year, or both. enables the user to find a specific entry, see all reports of a single year, or compare this year's emissions to last year's, to see progress more clearly.

#  Dependencies: 
### Dependencies to run the project:
## 1. Node Modules 
the modules in node used by the project must be installed, by running 
```npm install``` in the terminal (you need to have nodeJS installed).
Note: you will need to run this once in the parent folder and another time in the backend folder.

## 2. Database:
This project uses mongoDB to manage its data, make sure you have mongoDB installed, and the following structure (database and collections), is created.


![image](https://github.com/user-attachments/assets/22c69eaa-4448-407d-87c7-42ddec1e483c). 

To load predefined factors and make the application running without making any changes in the database, import the ```emissionfactors.json``` file into your emissionfactors mongo collection.
(This is a functional template for some emissionfactors, and can later be changed directly from mongoDB compass's UI.)

You can also run ```node seed``` in the backend folder's terminal to run a script that imports these collections.

## 3. Environment Variables: 
This project requires a .env file to run properly. For security reasons, the .env file is not included in the repository , you need to create one manually in the backend folder.

### Steps to Set Up:
1. Make sure you are in the project's backend directory and create a .env file.

2. Open your terminal and run the following Node.js script to generate a random string:

```node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"```

This command uses the crypto module in Node.js to generate a random sequence of 32 bytes and then  converts it to a hexadecimal string.
   
3. Copy the generated string. and write this statement in your .env file ```JWT_SECRET=generated-string``` where ```generated-string``` is the string generated from the node command.

4. Save the changes to your .env file.


# Run the Project:

Ensure connection to your mongoDB, and to start the backend server, run the command 

```node server``` 

in the backend directory terminal.

Now, your backend API should be up and running.

Ensure that your backend API is running, and to start the frontend server, run the command 

```npm run dev``` 

in the in the root directory terminal.
