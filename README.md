# Demo Spring Web Application for Performance Testing
## How to use
* Clone the project
    ```bash
        git clone https://github.com/RevatureGentry/DemoSpringWebApplication.git
    ```
* Inside the cloned directory, build the project using Maven
    ```bash
        mvn clean package 
    ```
* Run the Application, providing any JVM arguments as such
    ```bash
        java <JVM ARGS HERE> -jar target/DemoSpringWebApp.war
    ```
## Endpoints

| Method | URL | Description |
| ------ | --- | ----------- |
| GET | /login | Shows the Login Page |
| GET | /info | Shows the user information page |
| GET | /info/update | Shows the update user info page |
| GET | /register | Shows the Registration Page |
| GET | /todos | The authenticated home page, show table of all todos |
| GET | /todos/create | Shows the Create Todo Form |
| GET | /enable-dark-mode | Enables Dark Mode feature |
| POST | /process | Attempts authentication from form values |
| POST | /register | Attemps registration from form values |
| POST | /todos | Creates todo from Create Todo Form |
| POST | /logout | Signs the user out of the application |
| PUT | /todos | Marks the Todo by id at as completed. Id is found in request body |
| PUT | /info | Attempts to update user information |
| DELETE | /todos | Delete the Todo by id. Id is found in request body |

## Preloaded users

| Username | Password | Roles |
| -------- | -------- | ----- | 
| admin | Password123! | ROLE_ADMIN,ROLE_USER | 
| user2 | Password123! | ROLE_USER | 
| user3 | Password123! | ROLE_USER | 
| user4 | Password123! | ROLE_USER | 
| user5 | Password123! | ROLE_USER | 
| user6 | Password123! | ROLE_USER | 
| user7 | Password123! | ROLE_USER | 
| user8 | Password123! | ROLE_USER | 
| user9 | Password123! | ROLE_USER | 
| user10 | Password123! | ROLE_USER | 



# Performance Testing Lab

* You and your partner, employees of Acme, INC., have been tasked with verifying that the company's flagship product, [The Todos App](https://github.com/RevatureGentry/DemoSpringWebApplication), meets the following Service Level Agreements (SLA's):

​

## Service Level Agreements

* The application must be able to support 300 users concurrently over an 1 hour span

  * Page load after Sign In must complete in less than 650ms

  * Completing a Todo must complete in less than 800ms

  * Deleting a Todo must complete in less than 800ms

  * Posting to the Message Board must complete in less than 700ms

* User Registration must meet a throughput of 100 registrations/s

* User Sign in must meet a throughput of 150 logins/s

​

## Your Task

* Diagnose the application's performance and provide suggestions to code or configuration changes that will help you meet the provided SLA's

* Once you have your hypotheses and evidence, **_implement_** your proposed code or configuration change and retest to verify that the changes you made helped you towards meeting the SLA

* You cannot simply read through the code base and find the troublesome code

* You must supply evidence for **_every_** 

  * Hypothesis 

    * i.e. Response Times for the TodoService is degrading due to misconfigured isolation levels 

  * Suggestion 

     * this chart, comparing the Response Time for requests to `/todos` and Connection Pool Threads awaiting execution, supports my hypothesis by showing that Response Times are greater than the sample average when Connection Pool Threads awaiting execution is greater than _X_. This value was greater than _X_ for _Y_% of uptime

  * Verify

    * After modifying the isolation levels to a more appropriate assignment and rerunning our load test, we can review the same chart from our Suggestion that the sample average Response Time decreased _Z_%

​

### Potential Challenges and how to Overcome

* Some of your machines might not be able to support the application, along with our Monitoring tools, along with JMeter supplying 300 users concurrently... If this is the case, take 75% of the maximum load and complete the rest of the exercise using that value

​

### Charts/Figures to Consider

* Pertinent utilization, saturation, and errors measures

* Throughput vs Active Threads vs Idle Threads

* GC Throughput vs Application Throughput

* Heap Dumps

* Thread Dumps

* Code Snippets to replace existing functionality

* and many more...

​


