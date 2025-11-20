# Second Exercise: Salesforce CLI

## Explore Commands

1. Go back to your `learncli` directory. 

```
Windows
> cd ~\learncli

Mac
> cd ~/learncli
```

2. Type `sf update` to check that you're on the latest version of the Salesforce CLI. (this may be broken today).
3. Type `sf` to see all the CLI commands.
4. Find the command topics that allow you to:
    - Work with Salesforce objects
    - Test flows
    - Login to your org
5. Type `sf data query -h` to see the short help doc. 
6. Type `sf data query --help` to see the long help doc.

## Connecting to your org

> Note: you'll need to have created a **non production** org and have the username and password for the org for the way we'll authorize the Salesforce CLI. 

1. Type `sf project create -h` and read the help about how to create a project. 
1. Type `sf project create --name cli-project` to create a new project. 
1. Type `ls -al` and you'll see that there is a new folder for your project. 
1. Type `cd cli-project`
1. Type `sf auth web login -h`. 
1. Take a moment and read the basic help. 
1. Login to your org, you'll want to give your org an alias, and set it as the default org. 
    - `sf auth web login --alias learncli --set-default`
1. Complete the web login for the org to authorize the Salesforce CLI
1. When your browser states you're logged in and you can close it, close it. 
1. Return to the terminal as your active window if not already. 

## Test your org connection

1. Type `sf org display -h` to view the docs. 
1. Type `sf org display --target-org learncli`.
1. While the `target-org` parameter is important, you also set a default org for your project. 
1. Type `sf org display`.
1. Open your org from the terminal by typing `sf org open`. 

## Check your current org limits

1. Type `sf org list limits` to view your org limits. 
1. Now view the limits in XML format with `sf org list limits --json`. 

## Work with Salesforce data

1. Revisit the help for the query command with `sf data query -h`. 
1. Query your account records `sf data query --query 'SELECT Id, Rating, Name FROM Account`.
1. Now output your query as CSV `sf data query --query 'SELECT Id, Rating, Name FROM Account --result-format csv`.
1. Lastly, output your query `sf data query --query 'SELECT Id, Rating, Name FROM Account --result-format csv --output-file=accounts.csv`.
1. Let's go way bigger and query all private reports that have not been run in the last year: 
    - `sf data query --query 'SELECT Id FROM Report Using SCOPE allPrivate WHERE LastRunDate < LAST_N_DAYS:365' --result-format csv > reports.csv`