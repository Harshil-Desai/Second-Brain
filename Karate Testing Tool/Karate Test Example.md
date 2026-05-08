---
date: 2026-05-07
tags: [karate, testing, example]
source: ""
status: developing
---

# Karate Test Example

A small annotated `.feature` file showing the basics of a Karate test — `Background`, `Scenario`, GET, POST, response matching, and saving values for later steps.

```gherkin
Feature: Understanding the Basics

  # This is a comment — use # to add notes

  # Background runs before EVERY scenario
  Background:
    # Set the base URL — this comes from karate-config.js
    * url baseUrl
    # Print to console (helpful for debugging)
    * print 'Starting test...'

  # Scenario = one test case
  Scenario: Simple GET request — check if server is alive

    # Step 1: define the endpoint path
    Given path '/health'

    # Step 2: make the HTTP call
    When method GET

    # Step 3: verify the response
    Then status 200

    # Step 4: check response body
    And match response == { status: 'ok' }

    # Print the response (for learning)
    * print 'Response:', response

  Scenario: POST request — login example

    # Define variables
    * def email = 'admin@example.com'
    * def password = '<REDACTED — see note below>'

    # Make request
    Given path '/users/login'
    And request { email: '#(email)', password: '#(password)' }
    When method POST
    Then status 200

    # Check specific fields exist
    And match response.data.accessToken == '#string'
    And match response.data.user.email == email

    # Save data for next steps
    * def token = response.data.accessToken
    * print 'Got token:', token
```

> **Note:** the original version of this file had a real-looking email and password in plain text. Replaced with a placeholder. If you want a real test, store credentials in `karate-config.js` (or environment variables) and reference them with `#(email)` / `#(password)` style — never inline in the feature file.

Related: [[Karate Setup Guide]]
