

** Categorized Activity Lists**

1. Set up the HTML structure:
   - Create separate `<div>` elements for each activity category you want to display (e.g., education, recreational, social).
   - Add appropriate headings or labels for each category.

2. Write JavaScript code to fetch activities from specific categories:
   - Use the Fetch API or an AJAX library to send a GET request to the Bored API endpoint with the desired category as a parameter (e.g., `http://www.boredapi.com/api/activity?type=recreational`).
   - Handle the API response using the `.then()` method and extract the activities from the response data.

3. Update the HTML to display the activities in their respective categories:
   - Access the `<div>` elements for each category using their respective ids.
   - Use a loop to iterate over the fetched activities.
   - Create appropriate HTML elements (e.g., `<li>`, `<p>`) for each activity and append them to the respective category `<div>` using the DOM manipulation methods (`appendChild()`, `innerHTML`, etc.).

