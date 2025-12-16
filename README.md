Project Setup – Snapgram (Social Media App)

Date: 15 December 2025

Folder Structure Update

While creating the Snapgram social media application, we modified the default React project structure for better organization:

The assets folder is moved outside the src directory.

The existing src folder is deleted.

A new src folder is created.

Inside the new src, we create main.js, which serves as the entry point of the application.

Root Creation in main.js

In main.js, we create the React root using react-dom/client and attach it to the DOM element with a specific id.

Why the ! (Non-Null Assertion) is Used
document.getElementById('root')!


document.getElementById() can return two possible values:

an HTMLElement (if the element exists)

null (if the element does not exist)

createRoot() does not accept null as an argument.

Because of this possibility, TypeScript throws an error, assuming the value might be null.

Solution

To inform TypeScript that the element is guaranteed to exist, we use the non-null assertion operator (!).

The ! tells TypeScript:

“This value will not be null at runtime.”

This is safe because the root element (e.g., <div id="root"></div>) is always defined in index.html.

Important Note

The ! operator is TypeScript-only

It has no effect at runtime

It is removed during compilation

Summary

document.getElementById() → HTMLElement | null

createRoot() → requires HTMLElement

! → assures TypeScript that the value is not null