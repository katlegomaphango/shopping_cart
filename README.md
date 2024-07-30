# Shopping Cart

# Introduction
A lot of new programmers don’t know why understanding is important. They think they can just copy code from people and that’s enough to get by. BUT as soon as you get your first job you’ll need to solve some serious problems on your own.

The problems you’ll be solving in this project are designed to be realistic. As a professional, you’ll likely need to do things similar to this. Please make sure you 100% understand!

## Here’s the scenario
Imagine you are working for a hot new online shopping startup. You’ve seen online shopping, right? Go poke around on Takealot or Amazon if you haven’t.

On the online shopping site, users (people who want to buy stuff) navigate around and then add items to their shopping baskets. Once they are happy with their baskets, then they “checkout”, pay for their goodies, and await their delivery.

## Why data matters
As a techie, data will be a part of your life. You’re going to need to learn how to make this stuff dance.

For data scientists and data engineers, it’s pretty obvious why this is the case. But seriously, for any kind of developer, it’s friggin’ important.

Generally, developers need to work on programs that talk to other programs. And programs talk to each other by passing data structures back and forth.

# Get started with the project by understanding the data format
First of all, please download the data in this file. You can use it for testing out your methods.

If you look at the data you’ll see that what we have is a list or array of elements. Each element represents a single shopping basket.

Each shopping basket has a few different pieces:

1. email: this is the email address of the customer.
2. status: this can have a few different values:
   1. OPEN means that the person is still busy shopping.
   2. PAID means that the person has paid for the basket in full, they are waiting for delivery.
   3. DELIVERED means that the customer has paid for and received their stuff.
3. items: this is a list/array of all the things that a person added to the basket.

Each item in the shopping basket has a few properties of its own:

1. name: dah
2. quantity: how many of these does the person want to buy?
3. price: This is the price of a single item. The prices are in South African Rands.

For example, if there is an item in the shopping cart that looks like this:
```
{"name": "hamster", "quantity": 2, "price": 20}
```

Then it means that the person is buying 2 hamsters at a price of R20 each. So that’s R40 in total.

Please note that one person can have multiple baskets. If you look at the data, you’ll see that tshepo@umuzi.org has 4 baskets. Two have been delivered, one has been paid for (so he’s awaiting delivery) and one is open (so he’s setting up his next order).

## Working with JSON files
JSON is a lovely data format because it is easy for humans to read, and machines like it too.

## Write some methodality
### Get baskets belonging to a single customer
Write a method called get customer baskets that takes in two arguments:

* the email address of a customer
* a list/array of all the shopping baskets

The method must return a list/array of all the shopping baskets that belong to the customer with that email address.

If the customer has no shopping baskets then return an empty list/array.

This kind of data should be returned if someone@umuzi.org has only one basket.
```
[
  {
    email: 'someone@umuzi.org',
    status: 'PAID',
    items: [{
        "name": "hamster",
        "quantity": 2,
        "price": 20
      }]
  }
]
```
### Get a list of all the customer email addresses
Write a method called get all customers, the method should take the data array as an argument and should return a list of sorted customer email addresses. The list must have no duplicates.

### List all the items that have been paid for but not yet delivered
Write a method called get required stock, your method should take the data array as an argument and should return all the items that need to be sent out for delivery. You need to return data in the correct format. Just include the names and quantities of the items.
For example, if one customer paid for 2 hamsters and another customer paid for one hamster and a bag of sawdust then your method should return the following data structure:

```
[
    {"name": "hamster", "quantity": 3},
    {"name": "bag of sawdust", "quantity": 1}
]
```

### Get the total amount spent by a customer
Write a method called get total spent that takes an email address as an argument and the data array. The method must return the total amount that the customer has spent up until this time.
Note that if a basket has been delivered then it has been paid for.

### Top customers
Write a method called get top customers that takes the data array as an argument and returns a list/array of all the customers. The result should be ordered according to the total amount spent.

The returned data structure should be an array/list of dictionaries/objects showing the email addresses and the total amounts spent per customer.

Make sure the returned value matches the following structure:
```
[
    {"email": "tshepo@umuzi.org", "total": 1023.10},
    {"email": "maru@email.com", "total": 950},
    ... etc
]
```
Hint: You have already defined some methods that would be useful in finding this result. Call those methods.

### Get customers who have OPEN baskets
Write a method called get customers with open baskets that takes in the data array as an argument and returns a sorted list/array of email addresses for customers who have baskets that are open.
