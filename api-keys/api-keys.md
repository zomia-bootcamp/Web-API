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
Follow the [key-generator-guide](./expirement/key-generator-guide.md)


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

- Do not share your .env file publicly or commit it to version control systems like Git.
- Add the .env file to your project's .gitignore file to ensure it is not accidentally shared.
- Whenever you make changes to the .env file, restart your application for the changes to take effect.



Practice Session 3: Secure API Key Handling (15 minutes)
In this final practice session, we will tackle a scenario that requires you to implement secure API key handling within a web application. Apply the best practices discussed earlier to securely handle the API key. Consider encrypting the API key or implementing server-side authentication mechanisms to prevent unauthorized access. Share your implementations with the class and engage in discussions about different approaches to secure API key handling.

Practice Session 2: Making API Requests (15 minutes)
It's time to put our knowledge into action and make API requests using the API key we generated. We will use JavaScript to demonstrate the process. Follow along as we provide a code example of making an API request, including the API key in the request headers or parameters. Experiment with different endpoints and data types provided by the chosen API to retrieve and display relevant information. This hands-on practice will help solidify your understanding of using API keys to access data from web APIs.

Popular Web APIs (15 minutes)
Now that we understand the concept of API keys, let's explore some popular web APIs that require API keys for access. These APIs provide a wide range of functionalities and data that can enhance web applications. For example, weather APIs offer real-time weather data, social media APIs enable integration with popular social platforms, and mapping APIs provide features like interactive maps and geolocation services. Understanding how these APIs utilize API keys will broaden your understanding of their importance in web development.

Conclusion (5 minutes)

To ensure students have time to engage and practice code during the lesson, it's beneficial to intersperse interactive coding exercises throughout the lecture. Here's a suggested placement of code practice sessions within the breakdown of the lecture:

1. Introduction (5 minutes)
   - Briefly explain the concept of APIs and their role in web development.
   - Emphasize the importance of APIs in accessing external services and data.
   - Introduce the concept of API keys as a means of authentication and authorization.

2. Understanding API Keys (10 minutes)
   - Define what API keys are and their purpose in API interactions.
   - Explain how API keys serve as a secret passcode to access APIs and their associated services.
   - Discuss the security implications of API keys and the need to protect them.

3. Practice Session 1: Generating an API Key (10 minutes)
   - Instruct students to sign up for an API key from a provider of their choice.
   - Guide them through the process of obtaining an API key.
   - Encourage students to share their experiences and ask questions during this practice session.

4. Popular Web APIs (15 minutes)
   - Highlight some popular web APIs that require API keys, such as weather APIs, social media APIs, and mapping APIs.
   - Explain the functionalities and data these APIs provide.
   - Discuss the benefits of incorporating these APIs into web applications.

5. Practice Session 2: Making API Requests (15 minutes)
   - Provide a code example of making an API request using JavaScript and demonstrate how to include the API key.
   - Guide students through the process of making their own API requests using the provided code example.
   - Encourage experimentation and exploration with different API endpoints and data.

6. Best Practices and Security Considerations (10 minutes)
   - Discuss best practices for securely managing and storing API keys.
   - Emphasize the importance of keeping API keys private and avoiding exposure in client-side JavaScript code.
   - Explain techniques such as storing API keys on the server-side or using environment variables.

7. Practice Session 3: Secure API Key Handling (15 minutes)
   - Provide a scenario where students need to secure their API key within a web application.
   - Challenge students to implement the best practices discussed to ensure secure handling of the API key.
   - Encourage students to share their implementations and discuss their approaches.

8. Q&A and Conclusion (10 minutes)
   - Allow time for questions and answers to address any confusion or concerns.
   - Summarize the main points covered in the lecture.
   - Encourage further exploration of APIs and the utilization of API keys in web development.

By incorporating multiple practice sessions throughout the lecture, students have the opportunity to apply their knowledge immediately and solidify their understanding of concepts. It also promotes active learning and engagement during the lesson.
