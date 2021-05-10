# 🥑 Week 4 Whacks

## `What's wrong with the following endpoints?`

> `GET updateNote/:id`

`the name isn't "RESTful" as it uses a verb, it's also missing a forward slash "/" at the beginning to explain the path from the root`
---

> `DELETE notes/:id`

`it's missing a forward slash "/" at the beginning to explain the path from the root`
---

## `Write a resolver and a client query that matches the following mutation.`

    ```graphql
    # node
    type Mutation {
      addPizza(type: String, toppings: [String]): Pizza
    }
    ```

    ```js
    // node
    const resolvers = {
        Mutation: {
            addPizza: (parent, args) => {
                const queryType = args.type;
                const queryToppings = args.toppings;
                queryToppings.push("Anchovies");
                const newPizza = {
                    type: queryType,
                    toppings: queryToppings
                }
                // our imaginary json file data
                data.pizzas.push(newPizza);
                // adds a status field to let us know it succeded
                newPizza.status = 201
                return newPizza
            }
        }
    }
    ```

    ```graphql
    # browser
    mutation {
        addPizza(type: "large", toppings: ["Shrimp","Mayonnaise","Corn"])
    }
    ```

## What are the pros and cons of GraphQL versus REST?
`From a serving perspective GraphQL allows you to reduce the number of lines you write by reducing the number of endpoints you have to make, but the tradeoff is that it requires the user to know what they are doing, so writing documentation is important.`

`From a consuming perspective GraphQL allows you to write queries in a very natural way, but requires you to understand what you can do with the API you're using.`

## What is a migration?
`A migration is a script that represents a set of changes to a schema, that once ran will reflect those changes on a database.`

## Why are migrations useful?
`They are a form of version control for databases and their schema`

## Why are environment variables considered a best practice in software development?
`They allow users to not reveal private informations by keeping them local only`

# 🎉 Bonus

## `What are good tips you would give someone else for being a good debugger?`
`Trace your code from the beginning; Actually read the error message and the line it happens at; Triple check your syntax;`