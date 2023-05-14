
**Random Activity Generator**

1. Set up the HTML structure:
   - Create a `<button>` element with an appropriate label, such as "Get Random Activity".
   - Create a `<div>` element with an id to display the random activity.

2. Write JavaScript code to fetch a random activity from the Bored API:
   - Attach a click event listener to the button element.
   - Inside the event listener function, use the Fetch API or an AJAX library to send a GET request to the Bored API endpoint (`http://www.boredapi.com/api/activity`).
   - Handle the API response using the `.then()` method and extract the activity from the response data.

3. Update the HTML to display the random activity:
   - Access the `<div>` element using its id.
   - Set the `innerHTML` property of the `<div>` to the fetched activity, so it gets displayed on the webpage.
