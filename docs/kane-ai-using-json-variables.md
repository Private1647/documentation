---
id: kane-ai-using-json-variables
title: KaneAI - Utilizing JSON Variables for Assertions
hide_title: false
sidebar_label: JSON Variables
description: Learn how to use JSON variables in the KaneAI test cases for assertions
keywords:
  - lambdatest automation
  - lambdatest kaneai
  - kaneai scroll elements
  - kaneai sidebar scroll
url: https://www.lambdatest.com/support/docs/kane-ai-using-json-variables/
site_name: LambdaTest
slug: kane-ai-using-json-variables/
---

<script type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify({
       "@context": "https://schema.org",
        "@type": "BreadcrumbList",
        "itemListElement": [{
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://www.lambdatest.com"
        },{
          "@type": "ListItem",
          "position": 2,
          "name": "Support",
          "item": "https://www.lambdatest.com/support/docs/"
        },{
          "@type": "ListItem",
          "position": 3,
          "name": "KaneAI Jira Integration",
          "item": "https://www.lambdatest.com/support/docs/kane-ai-using-json-variables/"
        }]
      })
    }}
></script>
This document outlines the process of using JSON variables in KaneAI to assert specific objects within an API response. The guide provides a step-by-step procedure for executing API calls, examining responses, and performing assertions on both status and body of the response.

## Prerequisites
- Access to KaneAI platform
- Basic understanding of API testing
- Familiarity with JSON structures

## Step 1: Understanding JSON Variable Assertions
In KaneAI, you can use JSON variables to perform detailed assertions on API responses. This allows you to validate specific objects and elements within the response structure.

## Step 2: Initiating an API Call
- Navigate to your desired API endpoint (e.g., a pet store website)
- Configure the necessary API call parameters
- Execute the API request

### Example Workflow:
- Select the appropriate HTTP method (GET, POST, etc.)
- Add required headers
- Input any necessary request body
- Send the request

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image2.jpg').default} alt="Image" className="doc_img img_center"/>

## Step 3: Accessing Response Variables
After executing the API call, KaneAI automatically generates variables containing:
- Response status code
- Response body
- Response headers
- Other relevant metadata

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image3.jpg').default} alt="Image" className="doc_img img_center"/>

## Step 4: Asserting Response Status
To assert the response status:

- Use double curly braces `{{` to access the variable list
- Navigate using arrow keys to select the status variable
- Define your expected status code

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image4.jpg').default} alt="Image" className="doc_img img_center"/>

### Example:
- Expected status: 200
- If actual status is 500, the assertion will fail

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image5.jpg').default} alt="Image" className="doc_img img_center"/>

## Step 5: Asserting Response Body
Navigate through the response body using the same double curly brace method:
- Open the variable selection menu with `{{`
- Browse to the specific JSON element you want to validate
- Create an assertion for that element

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image6.jpg').default} alt="Image" className="doc_img img_center"/>

### Example Validation:
- Check if 'dogs' element exists in the response
- Verify specific property values
- Validate nested JSON structures

<img loading="lazy" src={require('../assets/images/kane-ai/knowledge-base/variables/json-variable/image7.jpg').default} alt="Image" className="doc_img img_center"/>

<br />

## Video Explanation
<video class="right-side" width="100%" controls id="vid">
<source src= {require('../assets/images/kane-ai/knowledge-base/variables/json-variable.mp4').default} type="video/mp4" />
</video>
