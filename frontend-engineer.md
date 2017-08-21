# Frontend Developer

## 1. Cartified!

Your task is to implement a basic shopping cart for a website, following these basic rules:

* the cart needs to be implemented as an AngularJS service
* the cart should be retrieved from the localStorage, where it's stored under the key `cart`
* every time an action is performed on the cart, it should be persisted on the localStorage
* the cart should only know about item IDs and their quantity
* you will write the cart by implementing the methods of the provided cart service in the code block below: please fork it and submit your implementation
* it should take you less than 1 hour to come up with an implementation, but we won't put any time limit for this challenge
* This is implemented with angular 1 . you can use Angular 1, Angular 2 , ReactJS, Vue or Vanilla JavaScript

``` javascript
angular.module('services.cart', [])
    .service('Cart', ['$rootScope', 'Reviewer', function ($rootScope, Reviewer) { 
        var getCart = function(){};
 
        var addItem = function(){};
 
        var addItems = function() {};
 
        var save = function() {};
 
        var remove = function () {};
 
        var clear = function() {};
 
        var persist = function() {};
 
        var changeQuantity = function (){};
 
        var refresh = function() {};
    }]);
```

### Methods explanation

For some of the methods mentioned in the empty Cart service, we thought of giving you some explanation to better understand what they're there for.

#### Save

Checks if the cart can be persisted through the `Reviewer` service: if so, it `persist`s it.

#### Clear

Empties the cart

#### Persist

Persist the cart on the localStorage

#### changeQuantity

Changes the quantity of one of the items in the cart.

#### Refresh

Notifies the application that the cart has been persisted, so that other parts of the app can modify themselves based on the latest cart update.

### Dependencies

You are not allowed to inject any dependency on the Cart service other than the ones provided:

* `$rootScope`: you might want to use it for whatever reason (for example, triggering events)
* `Reviewer`: it's an angular service that will review the contents of the cart (`Reviewer.review(cart)`, returns a promise)

### What are we going to look for?

* the fewer lines of code, the better
* clear, coincise, DRY implementation
* appropriate naming conventions

Another thing to consider: the cart should be working even when the user has multiple browser tabs open and is adding products from each of them.

We are **not** going to check the submitted script for syntax errors: concentrate on the design of the `Cart` service, we don't need to check for the small things

Please use **a simple one-file gist** (private or public) to submit your coding challenge.

## 2. CSS LESS AND BEAUTIFY

# Hacker Goods

Have you ever heard of hackernews? If you did, you know that it looks **quite bad**:

![HN](http://d1avok0lzls2w.cloudfront.net/img_uploads/SEOmoz-Hackernews-Rank.png)

What we request is to write make hackernews beautiful. **Really** beautiful.

You can fetch the HN data from the [unofficial API](http://api.ihackernews.com/page) and
use SASS, LESS, Stylus or whatever, the important thing is that the code is clean, consistent and crystal clear.

Add JS animations (jQuery or angular, we don't really care at this point :)) to make it spicy enough and then send us:

* 1 `index.html`
* 1 JS file
* 1 stylesheet (if you use a preprocessor, sends us the preprocessed one)

So that we can have a look at it!
