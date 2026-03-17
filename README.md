# Startup Idea Generator

A single-page web app that generates random startup ideas using the [ItsThisForThat API](https://itsthisforthat.com/api.php).

## How to Run

1. Clone or download this repository.
2. Open `home.html` using a local web server (e.g. the Live Server extension in VS Code).
3. Click the **Generate a startup idea** button to get a random idea.

> Note: Opening `home.html` directly as a file (`file://`) will cause a CORS error. Use Live Server or any local web server.

## Write-up

**API choice:** ItsThisForThat — a simple, no-authentication API that returns a random pair of concepts as JSON, formatted as `{"this": "...", "that": "..."}`.

**Functionality:** The app displays a button. When clicked, it fetches a random concept pair from the API via a CORS proxy and displays the result as "It's like [this] for [that]."

**Challenges:** The API does not send CORS headers, so direct browser requests are blocked by the browser's same-origin policy. This was resolved by routing requests through the `api.allorigins.win` proxy, which adds the required headers. Intermittent 500 errors from the proxy are handled by a `try/catch` block that displays a friendly error message.

## Test Cases

### Normal Cases

| # | Action | Expected Result |
|---|--------|----------------|
| 1 | Click the button once | A startup idea appears in the format "It's like X for Y" |
| 2 | Click the button again | A different (random) startup idea is displayed |
| 3 | Click the button multiple times | Each click produces a valid idea without breaking the page |

### Edge Cases

| # | Scenario | Expected Result |
|---|----------|----------------|
| 1 | Disconnect from the internet, then click the button | Error message "Sorry, the VC money ran out." is displayed |
| 2 | Reconnect and click again after an error | App recovers and displays a valid idea |
| 3 | Click the button rapidly multiple times | App does not crash; eventually displays a valid result or error message |

---

## Assignment Instructions

Objective: Develop a small web application that integrates with a third-party API of your choice. This assignment is designed to enhance your skills in API integration, understanding documentation, and creating a functional application based on an API's capabilities.

Project Overview:

You are free to choose any third-party API from this list of public APIsLinks to an external site..
Consider selecting an API that does not require authentication for simplicity.
Your task is to create an application that uses data from the selected API in a creative and useful way.
Project Requirements:

API Selection: Explore the provided list of public APIs and choose one that interests you. It could be anything from weather data, social media interactions, to public datasets.

Application Concept: Develop a concept for your application. What will it do? How will it use the data from the API? Consider what kind of problems it could solve or what kind of service it could provide.

Application Development: (Optional)

Design and implement a user interface for your application. 
Ensure your application consumes data from the API and displays it effectively. 
Implement proper error handling and data validation.
Documentation and Testing:

Write clear documentation on how your application works and how to set it up.
Test your application thoroughly to ensure it handles different scenarios gracefully.
Write up:

Prepare a short write-up explaining your choice of API, the functionality of your application, and any challenges you encountered during development.
Demonstrate the functionality of your application with examples.
 

Assignment Submission:
Once you have completed the assignment, please prepare the following for submission:

GitHub Repository:

Push your program to a new GitHub repository.
Ensure that your repository is public so that it can be accessed and reviewed.
Your repository should include all source code files and a README.md file that briefly describes the project and how to run it.
Demonstration:

Provide a video demonstrating your program in action. The demonstration should include:
Show the program's functionality.
You need to present test cases and demonstrate that you are passing those cases.(we expect you to have at least 3 test cases testing normal cases and at least 3 test cases testing edge cases)
Submission:

Submit the link to your GitHub repository.
Include a link to your video demonstration. Youtube link (public or unlisted)