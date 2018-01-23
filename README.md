# Clickful Backend Coding Test

## Introduction
Assume we have a web server for a search engine. HTTP requests to this system is 
handled by a load balancer which distributes requests randomly between 2 machines.

Your system architect has analysed the database queries and has concluded the operation
to perform each search is too expensive. 
 
He proposes that you implement a cache to improve performance. 

He is also very strict on testing, so he strongly recommends writing unit tests to test that your functions behave the way they're intended to :).

## Assignment

Design a caching mechanism for the 100 most recent queries. 

In addition to the basic 'get' and 'set' methods, your cache must have the following features:

- User of the cache should be able to configure the cache with a time-to-live (TTL) on instantiation. 
- A given key-value pair should be removed from the cache after the TTL expires. For example:
```js
// TTL = 2 minutes
// Given the following state in the cache:
{ 
  foo: 'bar', // added to cache at 9:59
  fooz: 'baz' // added to cache at 10:00
}
// If current time is 10:00, `foo: bar` should no longer exist on the cache at 10:01.
```
- The cache must be shared between 2 machines, so please consider and implement this in your solution.
- Using a testing framework (e.g. Mocha) and an assertion library (e.g. Chai) of your choice, write unit tests for your caching mechanism.
Here are some hints for things to cover in your tests: 

    - What happens if a user instantiates the cache with an invalid TTL (e.g. a string instead of a number)?
    - How will you test that your cache only contains values of the 100 most recent search queries?
    - How will you test that key-value pairs are being expired and removed properly?
 
## Requirements

- The cache must be implemented Javascript and run in Node.js (version 8+)
- Please do **not** use any external libraries. 
- Native Node.js modules **are** permitted.

## Criteria for evaluation

Your solution will be evaluated based on the following criteria:
- Is your API clean and easily testable?
- How easy is it to maintain your code? 
- Robustness - does your solution capture and handle edge cases appropriately?

## Brownie points :)

Deploy your solution to a hosting service of your choice (e.g. Heroku)