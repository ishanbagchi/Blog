# Shorten up huge URLs to a small link

Today I created a node app to get generate a small link for a long website link.

## How to use:

### Request

![request](https://ishanbagchi.github.io/Ishan-Tech-Blog/day5/images/request.PNG)

I am using [Hoppscotch](https://github.com/hoppscotch/hoppscotch) to play with my routes. You may use any tools like Hoppscotch, [Postman](https://www.postman.com/), etc. Here I am creating a POST request to the URL `https://ishan-us.herokuapp.com/api/url/shorten` with content type _application/json_ and a Parameter name _longUrl_ with the value of any large URL you want to compress. That's it!!!

### Response

![response](https://ishanbagchi.github.io/Ishan-Tech-Blog/day5/images/response.PNG)

View the response in a JSON format. you can see a response with status _200_. The longUrl is the actual site where the user will be redirected, and the shortUrl is your generated small URL. 

> I automated the workflow of this project with [GitHub Actions](https://github.com/features/actions).

It was my first ever Actions so I was super duper excited. After clicking the Actions option in my repository, the below page appeared

![Actions get started](https://ishanbagchi.github.io/Ishan-Tech-Blog/day5/images/actions-get-started.PNG)

I selected the set up your workflow yourself option to get started.

## My Workflow
The name of my Github Actions is `Node.js CI`. It runs the following code every time something is pushed on the master branch, or if a pull request is made to the master branch.

```bash
npm ci
npm run build --if-present
npm test
```

After I created my .yml file and ran my workflow, this page displayed after building.

![build image](https://ishanbagchi.github.io/Ishan-Tech-Blog/day5/images/actions-build.PNG)

## Submission Category: 

Wacky Wildcards

## Link to Code

[@ishanbagchi/url-shortner](https://github.com/ishanbagchi/url-shortner)

## Note: 

> The collaboration to the project is open to all.
