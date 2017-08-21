# Backend Developer 
### Your Codes must be written in PHP . You can use any framework(Yii2, CodeIgniter, Laravel, Sympony or Zend)

## 1. Events to the rescue!

Imagine you re working with a state-machine that triggers a generic `state.change` event.

```php
<?php

class StateMachine
{
   public function transitionTo($state)
   {
        try {
            // ...

            $eventDispatcher->dispatch('state.change', ['from' => $fromState, 'to' => $toState]);
        } catch (\WhateverException $e) {
            $this->rollback();
        }
   }
}
```

Let's say **you can't modify this state machine class** because it's a 3rd party module and your framework sucks so you cannot extend it.

Describe how you can provide a better API / implementation for dealing with state transitions in your userland code.

You can create as many classes as you wish, but your only external dependency you can use in your classes is the `$eventDispatcher`, which implements this interface:

```php
<?php 

interface EventDispatcher
{
    /**
     * Dispatches an event.
     */
    public function dispatch($eventName, array $parameters = array());

    /**
     * Attaches the $callable to an event, so that it will get executed 
     * once the event is dispatched.
     */
    public function on($eventName, $calllable);
}
```

3 fundamental rules / starting points:

* less is better
* simplicity over complexity
* declarative vs generic

Have fun!

## 1. Event Management API (Ticket Buying)

Your Boss said you need to Extend a website to sell tickets online. Create a  ticket model and an api to  add, edit, update ticket and also ticket type.YOur api should be able to :
* Get  all Ticket
* Add ticket
* Update Ticket Type
* Create ticket type
* Edit Ticket


Have fun!

## 2. Working with data

Write a data migration script to create the Database of the  neccesary model,  also create  the  Model Class for each of the table with the proper relationship.

## 3. Telecom APIs

This challenge should take you ~30 minutes of time (let's keep it simple) 
and isn't related to any particular language, you can even implement it 
in pseudo-code, as we're more interested in your software design skills
rather than knowing if you know all the `array_*` functions.

### Background

We are a TeleCom operator.

In our DB, we are starting to store phone numbers associated to customers (`1 customer : N phone numbers`) and we will provide an API to modify them.

We need 3 APIs:

* get all phone numbers
* get all phone numbers of a single customer
* activate a phone number

### Challenge

Provide us the API endpoints (and HTTP methods) used to implement those 3 APIs.

For each endpoint, describe a controller method (you decide which dependencies you can use) that implements the API.

### Example

```
API description:

retrieve a list of dogs

API endpoint:

GET example.org/api/dogs

API implementation:

function getDogs($req, $res, $db) {
    $dogs = $db->getAllDogs()->toArray();
    $res->setData($dogs);

    return $res;
}
```

Another example could be:

```
API description:

retrieve a list of dogs

API endpoint:

GET api.example.org/v1/dogs

API implementation:

function getDogs(list $criteria, $dogRepository) {
    $dogs = $dogRepository->filterBy($criteria);

    return httpResponse::create($dogs);
}
```

Feel free to use the design that **you** think is best! It might be that none of the examples are actually good ;-)
Also Send only the relevant code base ...Dont include the framework
