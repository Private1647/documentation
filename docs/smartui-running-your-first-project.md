---
id: smartui-running-your-first-project
title: Running Your First Project on SmartUI
hide_title: false
sidebar_label: Running Your First Test
description: Learn how to run your first project on smartui step by step guide for the first time users to help them understand how the platform works
keywords:
  - smart visual testing in lambdatest
  - visual  ui testing,image to image comparison
  - free cross browser testing tool
  - regression testing tool
  - perform visual ui testing online
  - compare image to image
  - internet explorer 9 browser test
  - test on samsung a7 online
  - test on mac 10.11 el capitan online
  - apple mac el capitan virtual machine
url: https://www.lambdatest.com/support/docs/smartui-running-your-first-project/
site_name: LambdaTest
slug: smartui-running-your-first-project/
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import CodeBlock from '@theme/CodeBlock';
import {YOUR_LAMBDATEST_USERNAME, YOUR_LAMBDATEST_ACCESS_KEY} from "@site/src/component/keys";

<script type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify({
       "@context": "https://schema.org",
        "@type": "BreadcrumbList",
        "itemListElement": [{
          "@type": "ListItem",
          "position": 1,
          "name": "LambdaTest",
          "item": "https://www.lambdatest.com"
        },{
          "@type": "ListItem",
          "position": 2,
          "name": "Support",
          "item": "https://www.lambdatest.com/support/docs/"
        },{
          "@type": "ListItem",
          "position": 3,
          "name": "Smart Visual Testing",
          "item": "https://www.lambdatest.com/support/docs/smartui-running-your-first-project/"
        }]
      })
    }}
></script>
This guide will walk you through the process of running your first visual regression test using SmartUI, a powerful feature of LambdaTest that ensures your web applications look flawless across all browsers and devices.
## Prerequisites

- Basic understanding of Command Line Interface and Selenium is required.
- Login to [LambdaTest SmartUI](https://smartui.lambdatest.com/) with your credentials.

The following steps will guide you in running your first Visual Regression test on LambdaTest platform using SmartUI Selenium SDK integration.

## Step 1: Create a SmartUI Project
The first step is to create a project with the application in which we will combine all your builds run on the project. To create a SmartUI Project, follow these steps:

- Go to [Projects page](https://smartui.lambdatest.com/) and click on the **New Project** button.
- Select the platform as <b>CLI</b> for executing your **SDK** tests.
- Add name of the project, approver's name, and tags for any filter or easy navigation.
- Click on the **Continue** button.

Now select your desired framework and click on the **Configure** button. For the demo purpose we will select the Java framework.

## Step 2: Configure your Test Suite dependencies

You can use your own project to configure and test it. For demo purposes, we are using the sample repository.

:::tip Sample repo
Download or Clone the code sample code repository from the LambdaTest GitHub repository to run the project on the SmartUI.

<a href="https://github.com/LambdaTest/smartui-java-testng-sample" target="_blank" className="github__anchor"><img loading="lazy" src={require('../assets/images/icons/github.png').default} alt="Image" className="doc_img"/> View on GitHub</a>
:::

- Add the following dependency in your `pom.xml` file

```xml title="pom.xml"
<dependency>
    <groupId>io.github.lambdatest</groupId>
    <artifactId>lambdatest-java-sdk</artifactId>
    <version>1.0.2</version>
</dependency>
```

:::note
You can check the latest version of [lambdatest-java-sdk]( https://mvnrepository.com/artifact/io.github.lambdatest/lambdatest-java-sdk) and update the latest version accordingly.
:::

- Install your CLI and required modules for running SmartUI SDK and compile your defined dependencies in the `pom.xml` file:

```zsh
npm i @lambdatest/smartui-cli
mvn clean compile
```

## Step 3: Setup your Project Token and Environment Variables

Setup your project token show in the **SmartUI** app after, creating your project.

<Tabs className="docs__val" groupId="language">

<TabItem value="MacOS/Linux" label="MacOS/Linux" default>
<div className="lambdatest__codeblock">
<CodeBlock className="language-bash">
{`export LT_USERNAME="${YOUR_LAMBDATEST_USERNAME()}"
export LT_ACCESS_KEY="${YOUR_LAMBDATEST_ACCESS_KEY()}"
export PROJECT_TOKEN="123456#1234abcd-****-****-****-************"`}
</CodeBlock>
</div>
</TabItem>

<TabItem value="Windows" label="Windows - CMD">
<div className="lambdatest__codeblock">
<CodeBlock className="language-bash">
{`set LT_USERNAME="${YOUR_LAMBDATEST_USERNAME()}"
set LT_ACCESS_KEY="${YOUR_LAMBDATEST_ACCESS_KEY()}"
set PROJECT_TOKEN="123456#1234abcd-****-****-****-************"`}
</CodeBlock>
</div>
</TabItem>

<TabItem value="Powershell" label="Windows-PS">
<div className="lambdatest__codeblock">
<CodeBlock className="language-bash">
{`$Env:LT_USERNAME="${YOUR_LAMBDATEST_USERNAME()}"
$Env:LT_ACCESS_KEY="${YOUR_LAMBDATEST_ACCESS_KEY()}"
$Env:PROJECT_TOKEN="123456#1234abcd-****-****-****-************"`}
</CodeBlock>
</div>
</TabItem>

</Tabs>

<img loading="lazy" src={require('../assets/images/smart-visual-testing/running-first-test/1.png').default} alt="cmd" width="768" height="373" className="doc_img"/>

## Step 4: Create and Configure SmartUI Config
You can now configure your project configurations on using various available options to run your project with the SmartUI integration. To generate the configuration file, please execute the following command:

```bash
npx smartui config:create .smartui.json
```
Once, the configuration file will be created, you will be seeing the default configuration pre-filled in the configuration file:

```javascript title="/smartui-sdk-project/.smartui.json"
{
  "web": {
    "browsers": [
      "chrome",
      "firefox",
      "safari",
      "edge"
    ],
    "viewports": [
      [
        1920
      ],
      [
        1366
      ],
      [
        1028
      ]
    ] // Full Page screenshots are captured by default for web viewports
  },
  "mobile": {
    "devices": [
      "iPhone 14",  //iPhone 14 viewport
      "Galaxy S24"  //Galaxy S24 viewport
    ],
    "fullPage": true, //Full Page is true by default for mobile viewports
    "orientation": "portrait" //Change to "landscape" for landscape snapshot
  },
  "waitForTimeout": 1000, //Optional (Should only be used in case lazy-loading/async components are present)
  "waitForPageRender": 50000, //Optional (Should only be used in case of websites which take more than 30s to load)
  "enableJavaScript": false, //Enable javascript for all the screenshots of the project
  "allowedHostnames": [] //Additional hostnames to capture assets from
}
```
:::info Advanced options in SmartUI configuration
- For capturing fullpage or viewport screenshots, please refer to this [documentation](/docs/smartui-sdk-config-options/#12-viewports)
- For the list of available mobile viewports, please refer to this [documentation](/docs/smartui-sdk-config-options/#list-of-supported-device-viewports)
- For more information about SmartUI config global options, please refer to this [documentation](/docs/smartui-sdk-config-options/#3-global-options-optional).
:::

## Step 5: Adding SmartUI function to take screenshot
You can incorporate SmartUI into your custom `Selenium` automation test (any platform) script by adding the `smartuiSnapshot` function in the required segment of selenium script of which we would like to take the screenshot, as shown below: 

```java
import io.github.lambdatest.*; //Importing the lambdatest-java SDK
//Rest of your code here

@Test
    public void basicTest() throws Exception {
        String spanText;
        System.out.println("Loading URL");

        driver.get("<Required URL>");
        // ... test code snippet
        // highlight-next-line
        SmartUISnapshot.smartuiSnapshot(driver, "<Screenshot Name>");
    }
```

## Step 6: Execute the Tests on SmartUI Cloud
Execute `visual regression tests` on SmartUI using the following commands

```bash
npx smartui --config .smartui.json exec -- mvn test -D suite=sdk-cloud.xml
```
:::note 
You may use the `npx smartui --help` command in case you are facing issues during the execution of SmartUI commands in the CLI.
:::

You can see the Smart UI dashboard to view the results. This will help you identify the Mismatches from the existing `Baseline` build and do the required visual testing.

<img loading="lazy" src={require('../assets/images/smart-visual-testing/smartui-sdk-results-primer.webp').default} alt="cmd" width="768" height="373" className="doc_img"/>