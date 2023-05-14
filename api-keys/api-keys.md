# Understanding API Keys in Web Development

## Objective:
* understand the concept of API keys 
* their role in accessing APIs
* secure handling of API keys.


## Introduction 
APIs are important tools in web development because they let different software systems talk to each other and share information. API keys are like secret codes that verify our identity and give us permission to use specific APIs. In this lesson, we'll learn about API keys and see how they keep our interactions with APIs secure.

## Understanding API Keys 
API keys are like special codes that give you access to certain APIs. They work as secret passcodes that allow you to use APIs and all the cool things they can do. For example, if you want to use the [Google Maps API](https://developers.google.com/maps) to show maps on your website, you'll need an API key. It's like having a secret key to unlock the door to the API. API keys are important because they keep things secure. Just like you wouldn't want to share your secret passcode with anyone, you need to keep your API key safe too. If someone gets hold of your API key, they could misuse it or access sensitive data. So **it's really important to protect your API key and make sure it stays a secret**.

### Generating an API Key 
To gain practical experience, we will walk through the process of generating an API key. Choose an API provider, such as [OpenWeatherMap](https://openweathermap.org/), and sign up for an account on their website. Once registered, follow their instructions to generate an API key specific to your account. This key will be unique to you and will serve as your access pass to the weather data provided by the OpenWeatherMap API.

### Expirement:

Now try it on your own!
Follow the [key-generator-guide](./expirement/key-generator-guide.md) to generate your first api key.


## Best Practices and Security Considerations
To ensure the security of API keys, it is essential to follow best practices.**Avoid exposing API keys in public repositories or client-side JavaScript code**, as they can be easily compromised. Instead, consider storing API keys on the server-side or using environment variables to keep them secure. By adhering to these practices, you protect sensitive data and prevent unauthorized access to APIs. Understanding the importance of securing API keys will help you develop robust and secure web applications.

## Using a Local .env File:
One recommended approach for storing API keys is by utilizing a local `.env` file. The `.env` file acts as a container for sensitive information and is not meant to be shared publicly. Instead, it remains on your local machine, providing a layer of security.

**Step 1: Install dotenv**

JavaScript has various libraries that allow you to access environment variables. One popular library is dotenv. To use it, you'll need to install it in your project using a package manager like npm. 

**Step 2: Create a .env File:**
Start by creating a new file in your project directory. Name it `.env.local`. Open the `.env.local` file to begin adding your API key.

**Step 3: Add the API Key:**

Add a new line in the file and write the variable name for your API key. For example, if your API key is for a weather API, you can use:

```
WEATHER_API_KEY=
```

After the equal sign `=`, add your actual API key without any quotes or spaces. It should look like this:
```
WEATHER_API_KEY=your_api_key_here

```
**Step 4: Save the .env File:**

After adding the API key to the `.env` file, save the file in the same directory as your project.

**Step 5: Load Environment Variables in Your Code:**

In the JavaScript file where you want to use the API key, import the `dotenv` package at the beginning of the file using the `import` statement:
```js
import dotenv from 'dotenv';
```
Additionally, you need to call the `config` method from the `dotenv` package to load the environment variables from the .env file:
```javascript
dotenv.config();
```
This line of code loads the environment variables from the .env file into your application.

#### Remember:

- Do not share your `.env` file publicly or commit it to version control systems like Git.
- Add the .env file to your project's `.gitignore` file to ensure it is not accidentally shared.
- Whenever you make changes to the `.env` file, restart your application for the changes to take effect.

### Expirement:

Copy the api key you generated fro AirLabs, and save it locally on your machine.


## Making API Requests 
It's time to put our knowledge into action and make API requests using the API key we generated. Follow along as I provide a code example of making an API request, including the API key in the request headers or parameters. 
```js
import dotenv from 'dotenv';
import fetch from 'node-fetch';

dotenv.config();

const apiKey = process.env.API_KEY;

// Function to make the API request
function getWeatherData(city) {
  const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}`;

  // Send the GET request to the API
  fetch(apiUrl)
    .then(response => response.json())
    .then(data => {
      // Process the API response
      console.log(data); // You can customize how you handle and display the data
    })
    .catch(error => {
      console.log('Error:', error);
    });
}

// Call the function with the desired city
getWeatherData('London');

```

In this example, we use the `import` statement to import the `dotenv` and `node-fetch` packages. The `dotenv.config()` line is used to load the API key from the `.env` file, and the API key is accessed via `process.env.API_KEY`.

## Let's Get Real - Air Quality Index Display:

### Group Activity:

* Use the AirLabs API to fetch air quality data for a specific location.
* Create a user interface where users can input their location or select it from a list.
* Retrieve the air quality index (AQI) from the API response and display it along with relevant information such as pollutant levels and health recommendations.
* Visualize the air quality index using different colors or icons to represent different levels of air pollution.

*Feeling lost? Ask chatGPT to break down the instructions to smaller tastks*


## Popular Web APIs 
Now that we understand the concept of API keys, let's explore some popular web APIs that require API keys for access. These APIs provide a wide range of functionalities and data that can enhance web applications. For example, weather APIs offer real-time weather data, social media APIs enable integration with popular social platforms, and mapping APIs provide features like interactive maps and geolocation services. Understanding how these APIs utilize API keys will broaden your understanding of their importance in web development.
