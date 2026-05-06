---
title: "Exploring Wapka’s Server Library: A Comprehensive Guide to Handling HTTP Requests with Lua"
date: 2024-01-25
lastmod: 2025-06-24
draft: false
description: "Learn how to use Wapka’s server library in Lua to handle HTTP requests, manage templates, set headers, and more. A complete guide with examples for web developers."
categories: ["Guides"]
tags: ["HTTP requests", "Lua sandbox", "Lua scripting", "server.error", "server.header", "server.template", "Wapka CMS", "Wapka server library", "web development"]
author: "Jonayed Hossan Gazi"
showToc: true
---
# Exploring Wapka’s Server Library: A Comprehensive Guide to Handling HTTP Requests with Lua

Wapka’s **server library** is a powerful tool within its [Lua Sandbox Environment](https://wapka.org), designed to handle incoming HTTP requests and manage server-side operations with ease. Built for the [Wapka web development platform and CMS](https://zuna.id/wapka/), the server library provides developers with a robust set of methods to control time, headers, templates, and responses, making it ideal for creating dynamic, secure, and high-performance web applications. In this SEO-optimized guide, we’ll dive into the full capabilities of the Wapka server library, its methods, use cases, and practical examples to help you unlock its potential.

## Why Use Wapka’s Server Library?

The server library is a cornerstone of Wapka’s Lua-based scripting environment, enabling developers to manage HTTP requests, customize server behavior, and deliver dynamic content. Combined with Wapka’s features like free SSL certificates, 100 GB of cloud storage, and a built-in HTTP server, the server library empowers developers to build everything from simple static sites to complex web applications. Its methods are easy to use, secure, and optimized for web development, making it suitable for beginners and experienced developers alike.

## Overview of the Wapka Server Library

The `server` library provides a collection of methods to handle various server-side tasks, such as formatting dates, setting HTTP headers, serving templates, and managing script execution. Below is a detailed breakdown of each method, including its parameters, return values, and practical use cases.

### 1\. `server.time()`

**Description** : Returns the current time as a Unix timestamp (seconds since January 1, 1970, 00:00:00 GMT).

**Syntax** : `server.time() : int`

**Parameters** : None

**Return Value** : Integer (Unix timestamp)

**Use Case** : Use `server.time()` to track the current time for logging, scheduling, or timestamp-based operations.

**Example** :

```
-- Log the current Unix timestamp
    server.log("Current timestamp: " .. server.time());
      

```
**Output** : Logs the current Unix timestamp (e.g., `1737042360`).

### 2\. `server.date()`

**Description** : Formats a local date and time based on a specified format string and optional timestamp.

**Syntax** : `server.date(string `

`, int ) : string`

**Parameters** :

  * `format` (required): Specifies the date format using characters like `d` (day), `m` (month), `Y` (year), `H` (hour), etc. (see full list in the user input).
  * `timestamp` (optional): A Unix timestamp. Defaults to the current time (`server.time()`).

**Return Value** : Formatted date string.

**Use Case** : Display formatted dates on your website, such as for blog posts or event schedules.

**Example** :

```
-- Display the current date in "YYYY-MM-DD" format
    server.send(server.date("Y-m-d"));
      

```
**Output** : `2025-06-12`

### 3\. `server.timezone()`

**Description** : Gets or sets the server’s timezone.

**Syntax** : `server.timezone([string ]) : string`

**Parameters** :

  * `timezone` (optional): A timezone identifier (e.g., `"Asia/Dhaka"`). If omitted, returns the current timezone.

**Return Value** : Current timezone (if no parameter is provided) or nothing (if setting a new timezone).

**Use Case** : Ensure accurate time displays for users in different regions.

**Example** :

```
-- Set timezone to Asia/Dhaka (UTC+06)
    server.timezone("Asia/Dhaka");
    server.send("Timezone set to: " .. server.timezone());
      

```
**Output** : `Timezone set to: Asia/Dhaka`

### 4\. `server.template()`

**Description** : Displays a static template file or a system default page (e.g., 404, 500).

**Syntax** : `server.template(mix , mix `

) : bool**Parameters** :

  * `path` (required): The path to a template file or a default template code (e.g., `200`, `404`).
  * `header` (optional): HTTP header or response code.

**Return Value** : `false` if the template fails to display; otherwise, the template is shown, and script execution ends.

**Use Case** : Serve static pages or handle error responses dynamically.

**Example** :

```
-- Display a custom template file
    if not server.template("/test.html") then
      server.error("Template File Not Found", 404);
    end
      

```
**Output** : Displays `test.html` or a 404 error if the file is not found.

### 5\. `server.header()`

**Description** : Sets or unsets an HTTP response header.

**Syntax** : `server.header(string , string , bool , int `) : void``

**Parameters** :

  * `name` (required): HTTP header name.
  * `value` (required): Header value (set to `nil` to unset).
  * `replace` (optional): `true` to replace existing headers, `false` to add multiple headers of the same type.
  * `code` (optional): HTTP response status code.

**Return Value** : None.

**Use Case** : Customize response headers for content types, caching, or custom metadata.

**Example** :

```
-- Set Content-Type to plain text
    server.header("Content-Type", "text/plain");
    server.send("This is plain text");
      

```
**Output** : Sends a plain text response with the appropriate header.

### 6\. `server.delay()`

**Description** : Introduces a delay in script execution for a specified duration.

**Syntax** : `server.delay(int ) : void`

**Parameters** :

  * `time` (required): Delay duration in milliseconds.

**Return Value** : None.

**Use Case** : Simulate processing delays or control execution timing for testing.

**Example** :

```
-- Delay execution for 3 seconds
    server.delay(3000);
    server.send("Delayed response");
      

```
**Output** : Sends the response after a 3-second delay.

### 7\. `server.terminate()`

**Description** : Stops all script execution and ends processing.

**Syntax** : `server.terminate() : void`

**Parameters** : None.

**Return Value** : None.

**Use Case** : Halt script execution after a specific condition is met.

**Example** :

```
-- Terminate after printing a message
    server.send("Hello from Wapka");
    server.terminate();
    server.send("This will not be displayed");
      

```
**Output** : `Hello from Wapka`

### 8\. `server.error()`

**Description** : Stops script execution and throws a custom error with an optional HTTP status code.

**Syntax** : `server.error(string , int `) : void``

**Parameters** :

  * `msg` (optional): Error message to display.
  * `code` (optional): HTTP response status code.

**Return Value** : None.

**Use Case** : Handle errors gracefully, such as unauthorized access or missing resources.

**Example** :

```
-- Check for user login and throw error if not logged in
    if not env.is_user then
      server.error("Only for logged-in users", 403);
    end
      

```
**Output** : Displays a 403 error with the message “Only for logged-in users”.

### 9\. `server.send()`

**Description** : Sends data directly to the HTTP response buffer.

**Syntax** : `server.send(string , bool , int `) : void``

**Parameters** :

  * `data` (required): Data to send in the response.
  * `raw` (optional): If `true`, sends raw data without processing.
  * `code` (optional): HTTP response status code.

**Return Value** : None.

**Use Case** : Deliver custom responses, such as JSON data or plain text.

**Example** :

```
-- Send a raw text response
    server.send("Hello, Wapka!", true, 200);
      

```
**Output** : `Hello, Wapka!`

### 10\. `server.log()`

**Description** : Logs a custom message to the HTTP customLog header for debugging.

**Syntax** : `server.log(string ) : void`

**Parameters** :

  * `msg` (required): Message to log.

**Return Value** : None.

**Use Case** : Debug scripts by logging messages to server logs.

**Example** :

```
-- Log a debug message
    server.log("Script execution started");
    server.send("Processing complete");
      

```
**Output** : Logs “Script execution started” to the server logs and sends “Processing complete” to the client.

## Practical Use Cases for the Server Library

The server library is versatile and can be used in various scenarios to enhance your Wapka projects:

  * **Dynamic Content Delivery** : Use `server.send()` and `server.header()` to deliver custom JSON or HTML responses based on user input.
  * **Error Handling** : Implement robust error handling with `server.error()` to manage invalid requests or unauthorized access.
  * **Template Management** : Serve static pages or fallback to error pages using `server.template()`.
  * **Time-Based Features** : Use `server.time()` and `server.date()` to display timestamps or schedule content.
  * **Debugging** : Log runtime information with `server.log()` to troubleshoot issues during development.
  * **Performance Optimization** : Introduce controlled delays with `server.delay()` for testing or rate-limiting scenarios.

## Getting Started with the Server Library

To start using the server library in your Wapka project:

  1. **Create a Wapka Account** : Sign up at <https://wapka.org> and create a project.
  2. **Access the Lua Sandbox** : Navigate to the scripting section in the Wapka control panel.
  3. **Write Lua Scripts** : Use the server library methods to handle HTTP requests and manage server behavior.
  4. **Explore Documentation** : Visit the [Wapka blog](https://wapka.org) for tutorials and advanced scripting guides.
  5. **Upgrade for More Resources** : Consider a premium plan for increased execution time and resources for complex applications.

## Conclusion

Wapka’s server library is a powerful toolset for handling HTTP requests and building dynamic web applications within the Lua Sandbox Environment. With methods like `server.template()`, `server.header()`, and `server.error()`, you can create responsive, secure, and efficient websites tailored to your needs. Whether you’re managing templates, formatting dates, or debugging scripts, the server library provides the flexibility and control required for modern web development.

**Ready to supercharge your Wapka projects? Visit<https://wapka.org> today, start scripting with the server library, and build your next web masterpiece!**
