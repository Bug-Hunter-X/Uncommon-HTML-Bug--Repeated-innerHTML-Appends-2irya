# Uncommon HTML Bug: Repeated innerHTML Appends

This repository demonstrates an uncommon bug in HTML related to the repeated use of `innerHTML` for appending content. While seemingly simple, repeated use of `innerHTML` can lead to performance issues and security vulnerabilities if not handled carefully.

## Bug Description

The bug arises from repeatedly using `innerHTML` to add new content to an existing element.  This approach becomes inefficient as the browser has to repeatedly parse and render the entire innerHTML, leading to performance degradation, particularly with large amounts of content.

Additionally, if user-supplied data is directly appended via `innerHTML` without proper sanitization, it opens the application to Cross-Site Scripting (XSS) attacks. Malicious JavaScript could be injected, compromising the security of the application.

## Solution

The recommended solution is to use DOM manipulation methods like `appendChild` or `insertBefore` to add elements to the DOM instead of repeatedly modifying `innerHTML`.  This approach is significantly more efficient as it directly manipulates the DOM tree, leading to faster rendering and less potential for security vulnerabilities.

This allows for fine-grained control over the process and enhanced performance, while the use of `textContent` avoids any XSS vulnerabilities when adding plain text.