# Bilira

Bilira is a project developed using the Java programming language, integrating modern test automation tools like Selenium, Cucumber, and Rest-Assured. It offers a comprehensive solution for test automation, data management, and API testing.

## Features

- *Java 17 Support*: Compatible with Java 17.
- *Selenium Integration*: Utilized for web automation.
- *Cucumber Test Framework*: Enables writing tests with the BDD (Behavior Driven Development) approach.
- *Rest-Assured*: Comprehensive support for API testing.
- *Reporting*: Automated reports via Maven Cucumber Reporting plugin.

## Technologies and Dependencies

### Core Technologies

- *Java*: Programming language.
- *Maven*: For project build and dependency management.

### Key Dependencies

| Dependency                | Version   | Purpose                               |
|---------------------------|-----------|---------------------------------------|
| Selenium Java             | 4.27.0    | Web automation                        |
| Cucumber Java             | 7.11.2    | BDD test framework                    |
| Rest-Assured              | 5.3.2     | API testing                           |
| JavaFaker                 | 1.0.2     | Mock data generation                  |
| Jackson Databind          | 2.16.0    | JSON processing                       |
| PostgreSQL                | 42.6.0    | Database connection                   |
| Gmail                     | 8.2.6     | Email testing                         |
| Jsoup                     | 1.18.3    | HTML and DOM processing               |

### Testing and Reporting

- *Maven Surefire Plugin*: For parallel execution and management of tests.
- *Maven Cucumber Reporting Plugin*: Generates user-friendly reports from JSON test results.

## Setup

Start by cloning the project:

bash
git clone https://github.com/testgbt/biLiraDec19.git
cd bilira


### Requirements

- *Java 17*
- *Maven 3.x*



# Google API for OTP System Login

This project allows users to log in to the system using *Google API* with OTP (One-Time Password) verification. The OTP verification system leverages Google’s authentication services to ensure a secure login flow.

## Project Requirements

To run this project, you need a registered user.

###  Maven Dependencies

Add the following Maven dependencies to your pom.xml file:

xml
<dependencies>
<!-- Google API Client Library -->
<dependency>
<groupId>com.google.api-client</groupId>
<artifactId>google-api-client</artifactId>
<version>1.34.0</version>
</dependency>

    <!-- Google OAuth2 Library -->
    <dependency>
        <groupId>com.google.auth</groupId>
        <artifactId>google-auth-library-oauth2-http</artifactId>
        <version>1.18.0</version>
    </dependency>

    <!-- JSON Parsing Library -->
    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.10.1</version>
    </dependency>

    <!-- Apache HTTP Client -->
    <dependency>
        <groupId>org.apache.httpcomponents</groupId>
        <artifactId>httpclient</artifactId>
        <version>4.5.13</version>
    </dependency>
</dependencies>


1. **Log in to Google Cloud Console:**  
   Visit the [Google Cloud Console](https://console.cloud.google.com/).

2. **Create a New Project:**  
   Click on the **New Project** option in the top-left corner and name your project.

3. **Enable APIs and Services:**  
   Navigate to **APIs & Services → Library** and enable the **Gmail API**.

4. **Create Credentials:**  
   Go to the **Credentials** tab and select **Create Credentials → OAuth 2.0 Client ID**.  (Don't forget to set the scope)

5. **Download Credentials File:**  
   Download the generated credentials in JSON format and save it as `test.json` in the root directory of your project.

- **Email Address:** Use a Gmail account to send OTP codes.
- **Credentials JSON File:** Copy the content of the downloaded file into the `src/test/resources/test.json` file in your project.

An example JSON file looks like this:  
{
"installed": {
"client_id": "YOUR_CLIENT_ID.apps.googleusercontent.com",
"project_id": "YOUR_PROJECT_ID",
"auth_uri": "https://accounts.google.com/o/oauth2/auth",
"token_uri": "https://oauth2.googleapis.com/token",
"auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
"client_secret": "YOUR_CLIENT_SECRET",
"redirect_uris": [
"http://localhost"
]
}
}




Install the dependencies by running the following command:



bash
mvn clean install


## Project Structure

- `src/main/java`: Main application code.
- `src/test/java`: Test code.
- `runners`: Classes for running Cucumber scenarios.
- `resources`: Feature files and other resources.

##In the configuration.properties file, set the account information for token acquisition.

configurations.properties

email2 = ************@gmail.com
password2 = ************

email2 = *************@gmail.com
password2 = ************

tokenDirectoryPath=Tokens/ReceiveTokens
jsonDirectoryPath=src/test/resources/test.json


## Maven Commands

- To run all tests:

bash
mvn test


- To generate reports:

bash
mvn verify


## Customization

To modify parallel execution or other Surefire settings, update the relevant configurations in the `pom.xml` file:

xml
<parallel>methods</parallel>
<threadCount>2</threadCount>
<forkCount>2</forkCount>
```


MIT License

Copyright (c) [2024] [Bilira]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.