# Random Bible Verse

## Overview

This project is a simple web application that displays a daily random Bible verse each time a button is clicked. The main purpose of this project is to provide an easy way to read and reflect on a random Bible verse daily. The application uses an API to fetch the verses and displays them in a visually appealing format.

## Motivation

I was struggling to read the Bible consistently and felt that my faith was lacking. To address this, I decided to create a website that could help me read the Bible more regularly by displaying random verses. By starting with small, manageable steps, such as reading one verse at a time, I hope to slowly build a habit of daily Bible reading. Additionally, I plan to tag this application to an NFC tag and attach it to my bracelet, allowing me to access my daily Bible verses on the go.

## Features

- **Random Bible Verse:** Displays a random Bible verse each time the "New Verse" button is clicked.
- **Loading Spinner:** Shows a loading spinner while the verse is being fetched.
- **Responsive Design:** The application is designed to be visually appealing and easy to read on various devices.

## Technologies Used

- **HTML:** Structure of the web page.
- **CSS:** Styling the web page for a visually appealing layout.
- **JavaScript/jQuery:** Fetching random Bible verses from an API and updating the page content dynamically.
- **Google Fonts:** Custom font for headings and verse text.

### API Used

- [Bible API](https://labs.bible.org/api/?passage=random&type=json&callback=myCallback)

## Usage

1. Open the web page in a browser.
2. Click the "New Verse" button to fetch and display a random Bible verse.
3. The verse will be displayed in the verse container, along with the book name, chapter, and verse number.

## Code Explanation

### HTML

- `<!DOCTYPE html>`: Declares the document as an HTML5 document.
- `<head>`: Contains metadata about the document, including the title and links to external resources such as stylesheets and fonts.
  - `<title>`: Sets the title of the web page.
  - `<link rel="stylesheet" href="style.css">`: Links to the external CSS file for styling the page.
  - `<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Playfair+Display...">`: Links to a Google Fonts stylesheet for custom fonts.
- `<body>`: Contains the main content of the web page.
  - `<div class="container">`: A container for centering and styling the main content.
  - `<h1 class="heading">`: Displays the main heading of the page ("Daily Bible Verse").
  - `<div class="verse-container">`: Holds the Bible verse and the button to fetch a new verse.
  - `<div id="newQuote">`: Placeholder where the fetched Bible verse will be displayed.
  - `<div class="button-container">`: Holds the button and loading spinner.
  - `<button id="newVerseBtn">`: A button to fetch a new Bible verse.
  - `<div id="spinner">`: A loading spinner that is hidden by default and displayed while fetching a new verse.
- `<script src="...jquery.min.js">`: Includes the jQuery library for simplifying JavaScript coding.
- `<script src="script.js">`: Links to the external JavaScript file that contains the functionality for fetching and displaying the Bible verse.

### JavaScript

- `$(document).ready(function())`: Ensures the code runs only after the document is fully loaded.
- `$("#newVerseBtn").click(function())`: Attaches a click event handler to the "New Verse" button. When the button is clicked, it triggers the `getVerse` function.
- `var getVerse = function() { ... }`: Defines the `getVerse` function.
  - `$("#spinner").show()`: Shows the loading spinner to indicate that a request is in progress.
  - `$.ajax({ ... })`: Makes an AJAX request to the Bible API to fetch a random verse.
    - `url`: Specifies the API endpoint for fetching a random Bible verse.
    - `crossDomain`: Allows cross-domain requests.
    - `dataType`: Specifies the data type as JSONP (JSON with padding) to handle cross-domain requests.
    - `success`: A callback function that runs when the request is successful.
      - `$("#newQuote").html()`: Updates the `newQuote` div with the fetched Bible verse.
      - `$("#spinner").hide()`: Hides the loading spinner once the verse is successfully fetched.
- `getVerse()`: Initial call to fetch a Bible verse when the page loads, ensuring the page displays a verse as soon as it is opened.

## Future Enhancements

- **NFC Tag Integration:** Attach an NFC tag to the application so it can be accessed on the go.
- **Mobile Optimization:** Further optimize the design for mobile devices.
- **Additional Features:** Add more features such as sharing the verse on social media or saving favorite verses.

## Issues

### Backend Implementation

Initially started with an npm project file, which required manually storing Bible verses within the program.

### PDF Extraction

Created a Python program to extract verses from a PDF using pdfminer.six. Encountered issues where the program couldn't accurately recognize the end of a verse, resulting in either half a verse or nothing at all.

### API Search

Spent considerable time finding a suitable API to retrieve Bible verses.

### CORS Problem

Faced Cross-Origin Resource Sharing (CORS) issues where the browser blocked API requests due to origin restrictions. This required looking for ways to handle or bypass the CORS restrictions.

### Solution

Eventually found an API without CORS restrictions, which allowed the project to proceed smoothly and achieve its intended functionality.
