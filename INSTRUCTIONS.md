# Module 4 Exercise: MySQL Practice

(**NOTE:** View a rendered version of this file in VS Code with `ctrl-shift-v` or `cmd-shift-v`)

This exercise is intended to let you practice using SQL and MySQL on your own to design and query a database.

**WARNING:** This exercise uses Docker in its NPM scripts. **Please make sure that you do not have spaces or capital letters in your directory names.** You can check the path of your assignment using `pwd` in the terminal from within the folder on your machine. If you see spaces or capital letters, please change them to underscores or lower case characters.

&nbsp;
## Getting Started

This exercise uses the same program from the module assignment that allows you to run SQL files against a database. However, you may also use any MySQL tool to work with your database. All the included program does is look in the `queries` folder and offer to run those files against the database.

To get started, `cd` into the `unsolved` folder and run `npm i` to install the program dependencies.

&nbsp;
## Creating Tables and a Simple Query



The next thing you should do is to create the schema and seed data for your database. For this exercise, you should create a database for tracking different types of pizza.

First, make a table to store the names of pizzas (ex: pepperoni powerhouse, supreme, etc.) in the `schema.sql` file. You don't have to worry about running a command to create the database because the docker scripts already create a `pizza_db` database for you.

Next, in the `seed.sql` file, write some `INSERT` statements to create some pizzas.

Finally, create a file called `list_pizzas.sql` in `queries` and write a `SELECT` statement to fetch the list of pizzas.

When finished, try running the program with `npm start`. From the menu, select your `list_pizzas.sql` file and run it.

**NOTE**: If you notice that your database fails to start, this could be an error in your SQL syntax in either your schema or seed file. To debug, run `npm run mysql:start:log`. This command will start the database attached to the terminal output so you can see what errors are occuring. Modify your queries and run this command again. If there are no errors and the database starts, stop that process and run `npm start`.

&nbsp;
## Adding More Queries

After you've verified your database is working, try adding some more query files:
    
- Create a query for deleting a single pizza.
- Create a query for changing the name of a pizza.
- Create a query that counts the total number of pizzas.
- Create a query that sorts pizzas alphabetically.

&nbsp;
## Going Further

The above exercise will help you get started in MySQL and databases, but I suggest digging a little deeper. You'll often need to relate data in your tables, so let's practice that as well.

Think about adding toppings data to your database. How would you store toppings in your database? What kind of relationship would be appropriate for this data to associate toppings with pizzas? Go ahead and add toppings to your database by modifying the schema and seed files, then write the following queries:

- List pizzas and all of their associated toppings.
- List all pizzas that contain a particular topping.

<details>
    <summary style="cursor: pointer"><strong>Give up?</strong> (Toppings table association solution)</summary>
    
 I would suggest a many-to-many relationship for pizzas and toppings. You'll need to make an intermediary table that contains `pizza_id` and `topping_id` columns and then double join them to get the above queries. See the example queries from the assignment and the lectures.
</details>
