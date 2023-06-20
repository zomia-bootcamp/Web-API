# Web-API

## Objectives

- Understand the basics of working with APIs
- Implement API requests using JavaScript
- Integrate API data into HTML/CSS webpages
- Handle errors and provide error handling
- Enhance user interactivity and experience
- Apply best practices and security considerations

## Preparation

1. Fork and clone this repository.
2. Create a new branch called `training` for your work.
3. Install the necessary dependencies using `npm install`.


## Welcome to the wonderful world of web APIs! 🌐✨

Web APIs, or Application Programming Interfaces, are like magical portals that connect different software applications on the web. They allow developers, like you, to tap into the amazing powers of various web services and platforms.

Imagine being able to use social media features, payment gateways, mapping services, weather data, and more, all within your own applications. Well, web APIs make that possible!

![api](https://www.grapecity.com/componentone/docs/webapi/online-webapicore/images/webapi_core.png)

To embark on this exciting journey, here's a step-by-step guide to using web APIs:

## Step 1: Explore the API
Begin by exploring the API's official documentation, your ultimate guide to unlocking its secrets. It provides all the details you need about available features, methods, data formats, and how to play by the rules.

### Expirement
Visit [boredapi.com](http://www.boredapi.com/) and immerse yourself in the realm of limitless possibilities. The Bored API is here to rescue you from monotony by offering a vast array of activities for every mood and interest.

## Step 2: Craft Your API Request

To communicate with a Web API, we need to create a request. Think of it as composing a friendly message to your favorite website or service, kindly asking for something specific. Just like sending a secure letter, API communication is done over [HTTPS](https://developer.mozilla.org/en-US/docs/Web/HTTP), ensuring a safe and encrypted connection.

![url structor](https://cdn.ttgtmedia.com/rms/editorial/020619_TSS_RESTful-URL_half_column_mobile.png)

In our request, we'll include important details:
* **URL**: The web address of the API we want to interact with. 
* **Endpoint and Parameters**: Every API has its own set of magical doors, called endpoints. You'll need to knock on the right door and provide any necessary parameters, which are like extra notes that refine our request. It's like whispering the secret password to gain access!
* **API Key or Authentication**: Sometimes, the API may require special keys or tokens to verify our identity and ensure we have the proper authorization. Don't worry, it's as simple as registering your app and obtaining your own "key to the kingdom."

Let's use JavaScript to craft our API request. We'll employ the mighty [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) function to send a request and retrieve delightful activity suggestions.

In JavaScript, when we use the `fetch` function to make a request to a server, it returns a promise. A promise is like a guarantee that something will happen in the future. It's similar to the pizza place telling you that your pizza will be ready soon.

Being promise-based means that `fetch` allows us to handle the server's response in an asynchronous way. We can attach `.then()` and `.catch()` methods to the promise returned by `fetch` to handle the successful and failed responses, respectively. This allows us to write clean and readable code that waits for the response before executing further actions.

In essence, `fetch` being promise-based ensures that we can interact with server data in a smooth and organized manner, making our JavaScript code more reliable and efficient.

To fetch a random activity, we can create a function like this:

```js

    fetch(URL)
	.then((res) => res.json())
	.then((data) => {
		// Let's have some fun with the data!
		console.log(data)
	})
	.catch((error) => {
		// Oops! Something went wrong. Let's handle the error gracefully.
		console.error(error)
	})

```
### Expirement
Explore other options and parameters provided by the API. The documentation on the [Bored API website](http://www.boredapi.com/) is your trusty guide to unveil all the enchanting features available.

In [api.js](./expirement/api.js), write functions to fetch the correct data for the following cases:
* An activity for 3 participants
* An educational activity
* Low budget activity. the cost should be from $5 to $10.
The functions you created will send a request and return a Promise, allowing you to handle the response gracefully.

## Step 3: Embrace the Response

Once we've sent our request, it's time to patiently wait for the response, like receiving a message in a bottle from the API. 
The response will arrive with a special gift called [JSON](https://en.wikipedia.org/wiki/JSON) (JavaScript Object Notation). 
JSON is a format for representing data that's easy for both humans and computers to understand.

![json](https://www.w3resource.com/w3r_images/jsonviewer.stack.hu-format.png)

Inside the `.then()` method, we can access the JSON response, and let creativity flow. 

### Expirement

Use the activity suggestion you received in the [api.js](./expirement/api.js), to display it on your website. Here are two ideas to how you can use this data:
* Random Activity Generator: Retrieve a random activity from the Bored API and display it on your webpage. You can create a button or a link that, when clicked, fetches a random activity from the API and dynamically updates the HTML to show the activity.
* 
*Feeling lost?*
Use this [Step by step guide](./expirement/activity-generator-guide.md)

* Categorized Activity Lists: The Bored API provides activities categorized by type (e.g., education, recreational, social). You can fetch activities from specific categories and display them in separate sections on your webpage. For example, you could have a section for educational activities, another for recreational activities, and so on.
* 
*Feeling lost?*
Use this [Step by step guide](./expirement/categorized-activities-guide.md)




**Error Handling**: Even in the enchanting world of APIs, things can sometimes go awry. But fear not! By anticipating and handling errors gracefully, you can ensure a smooth and magical experience for your users. Be prepared to troubleshoot and overcome challenges like a true wizard.
To add an error handler to the code, follow these instructions:

1. Locate the section of the JavaScript code where you are making the API request (in both Idea 1 and Idea 2).

2. Add a `.catch()` method after the `.then()` method to handle any errors that may occur during the API request.

3. Inside the `.catch()` method, define a callback function that will execute when an error occurs. This function will receive an `error` parameter.

4. In the error callback function, you can perform the following tasks:
   - Display an error message on the webpage to inform the user about the issue.
   - Log the error details to the browser console for debugging purposes.
   - Disable or modify any affected UI elements as necessary.

Here's an example of how you can modify the code to include an error handler:

```js

fetch('http://www.boredapi.com/api/activity')
  .then(response => response.json())
  .then(data => {
    // Display the random activity on the webpage
    const activityDiv = document.getElementById('activity');
    activityDiv.innerHTML = data.activity;
  })
  .catch(error => {
    // Handle any errors that occur during the API request
    console.error('An error occurred:', error);
    // Display an error message on the webpage
    const activityDiv = document.getElementById('activity');
    activityDiv.innerHTML = 'Oops! Failed to fetch a random activity. Please try again later.';
  });
```

With these modifications, if an error occurs during the API request, an error message will be displayed on the webpage, and the error details will be logged to the console for debugging purposes.


### Expirement

Now it's your turn!
Add an error andler to your code in [api.js](./expirement/api.js).
Make sure to replace the URLs and element IDs with the appropriate values for your code.

## API Best Practices: 
Just like any great adventure, there are some best practices to follow. These might include optimizing your requests, using caching wisely, respecting rate limits (like taking breaks during your magical exploration), and keeping everything secure with HTTPS.

Remember, each API has its own unique features and guidelines, so make sure to consult the documentation and embrace the magic within.

Happy API adventures! ✨🚀🌈



