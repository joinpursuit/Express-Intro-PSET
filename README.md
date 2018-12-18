# Express Intro PSET

## Problem 1

Make an express server that serves the following routes:

- `/math/add`
- `/math/subtract`
- `/math/multiply`
- `/math/divide`

Each of these routes should take in two query parameters `a` and `b`.

Running a `GET` request on these routes should result in the following:

```javascript
GET localhost:3000/math/add?a=2&b=2
/*
  {
    result: 4
  }
*/

GET localhost:3000/math/subtract?a=2&b=2
/*
  {
    result: 0
  }
*/

GET localhost:3000/math/multiply?a=10&b=2
/*
  {
    result: 20
  }
*/

GET localhost:3000/math/divide?a=10&b=2
/*
  {
    result: 5
  }
*/
```

Make sure to break up your code into the appropriate modules and subfolders. We already built a module before that does this kind of math operations.

## Problem 2

Using the following unsplash API: `https://source.unsplash.com/1600x900/?nature,water`, lets make our own API with the following path: 

- `/image`

This route will take in the following queries: 
 - `?search=`
 - `&width=`
 - `&height=`

Running a GET request on these routes should result in the following:

```
GET localhost:3000/image?search=water?width=300&height=300
```
<img src='https://source.unsplash.com/300x300/?water'>

```
GET localhost:3000/image?search=model?width=100&height=100
```
<img src='https://source.unsplash.com/100x100/?model'>

## Problem 3

Install the following NPM module: `npm install uuid --save` 

You will be using this NPM module to generate a random unique identifier string like the following: `45745c60-7b1a-11e8-9c9c-2d42b21b1a3e`

We will be upgrading the functionality of the route we created in Problem 2. This time invoking the image search URL should not only return the image to the browser, but ALSO save and store the image locally.

Running the following: 
```
GET localhost:3000/image?search=water?width=100&height=100
```
Would not only respond with the following image:

<img src='https://source.unsplash.com/100x100/?water'>

But we will ALSO save this image with an unique name locally in the images/ folder:

```
/app
  node_modules/
  services/
  index.js
  images/
      45745c60-7b1a-11e8-9c9c-2d42b21b1a3e.jpg
```

So in this case the image was stored into the file `45745c60-7b1a-11e8-9c9c-2d42b21b1a3e.jpg`

