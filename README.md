## What is performance testing?
Is a non-functional testing approach to ensure that the application and the isolated elements of it will perform well under expected workload.
## What is JMeter?
JMeter is an open-source Java-based tool primarily used for performance testing web applications. 

# Content

- [Load testing Report](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#load-testing-report)  
- [Summary](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#summary)  
- [Introduction](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#introduction)  
- [Install](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#install)      
- [Prerequisites](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#prerequisites)   
- [Elements of a Minimal Test Plan](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#prerequisites)    
- [Creating a Test Plan](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/README.md#creating-a-test-plan)
- [Running The Test](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/README.md#running-the-test)
- [Test Plan](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/tree/main?tab=readme-ov-file#test-plan)

## Load testing Report

| Concurrent Request  | Loop Count | Avg TPS for Total Samples  | Error Rate | Total Concurrent API request |
|               :---: |      :---: |                      :---: |                        :---: |      :---: |
| 1  | 1  | 1.54| 0%      | 6  |
| 100  | 1  |  49.18    | 0%      | 600   |
| 500  | 1  |  183.70   | 0%   | 3000   |
| 1000  | 1  |  117.23  | 0%   | 6000   |
| 2000  | 1  |  211.18  | 0%   | 12000  |

## Summary

- Server can handle almost concurrent 2000 API call with almost zero (0) error rate.

## Introduction

This document explains how to run a performance test with JMeter against a Booking Site.

## Install

**Java**  
https://www.oracle.com/java/technologies/downloads/

**JMeter**  
https://jmeter.apache.org/download_jmeter.cgi  

Click =>Binaries    
=>**apache-jmeter-5.6.2.zip**

## Prerequisites

- As of JMeter 4.0, Java 8 and above are supported.
- we suggest  multicore cpu's with 4 or more cores.
- Memory 16GB RAM is a good value.

## Elements of a minimal test plan

- Thread Group

    The root element of every test plan. Simulates the (concurrent) users and then run all requests. Each thread simulates a single user.
- HTTP Request Default (Configuration Element)
- HTTP Request (Sampler)
- Summary Report (Listener)

## Creating a Test Plan

The first step in using JMeter is to create a Test Plan. A Test Plan is a collection of elements that define the test scenarios and their configurations. To create a Test Plan, you need to follow these steps:

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/Thred%20Group%20create.png)

1. Right-click on the Test Plan in the tree view on the left-hand side of the JMeter interface.
2. Select Add > Threads (Users) > Thread Group.
3. In the Thread Group panel, you can set the number of threads (users) to simulate, the ramp-up period, and the loop count.
4. Next, you need to add a Sampler element to the Thread Group. A Sampler is used to simulate a request to the server under test. To add a Sampler, right-click on the Thread Group, select Add > Sampler, and then choose the appropriate Sampler type (e.g., HTTP Request, JDBC Request, etc.)

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/1_.png)

5. In the Sampler panel, you can configure the parameters of the request (e.g., URL, method, parameters, etc.)

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/2_.png)

6. Finally, you can add a Listener element to the Thread Group to view the test results. A Listener displays the test results in various formats such as tables, graphs, and charts. To add a Listener, right-click on the Thread Group, select Add > Listener, and then choose the appropriate Listener type (e.g., Summary Report, Graph Results, etc.).

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/3_.png)

## Running The Test

Once you have created the Test Plan, you can run the test by clicking on the green arrow in the toolbar. JMeter will start sending requests to the server under test, and you can view the test results in the Listener.

Try Now
In this tutorial, we’ll go over how to set up a basic load test using JMeter to test the [https://restful-booker.herokuapp.com/booking](https://restful-booker.herokuapp.com/booking) API.
Set up the restful-booker.herokuapp.com/booking key by signing up to the above website. Then provide the API request details to the JMeter test plan.

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/4_.png)

After running the load test, you can view the responses and check the number of requests as well.

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/5_.png)

I have adjusted the thread group to have 1, 100, 500, 1000, 2000 concurrent users and do a load test.

![c](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/6_.png)

- Name: Users
- Number of Threads (users): 1, 100, 500, 1000, 2000
- Ramp-Up Period (in seconds): 10
- Loop Count: 1  

  1) The general setting for the tests execution, such as whether Thread Groups will run simultaneously or sequentially, is specified in the item called Test Plan.

  2) All HTTP Requests will use some default settings from the HTTP Request, such as the Server IP, Port Number, and Content-Encoding.

  3) Each Thread Group specifies how the HTTP Requests should be carried out. To determine how many concurrent "users" will be simulated, one must first know the number of threads. The number of actions each "user" will perform is determined by the loop count.

  4) The HTTP Header Manager, which allows you to provide the Request Headers that will be utilized by the upcoming HTTP Requests, is the first item in Thread Groups.

# Collection of API

### List of API 

  - For creating Booking: [https://restful-booker.herokuapp.com/booking](https://restful-booker.herokuapp.com/booking)
  - For getting, updating, deleting  Booking: [https://restful-booker.herokuapp.com/booking/id](https://restful-booker.herokuapp.com/booking/1)

### Load the JMeter Script 

   - File > Open (CTRL + O)
   - Locate the "BookingApp_csv_dataset_t1.jmx" file contained on this repo
   - Continue open BookingApp_csv_dataset_t1 to BookingApp_csv_dataset_t2000
   - Open those file
   - The Test Plan will be loaded  
   
   ![testPlan](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/Project%20Screenshot/opening-Jmx-File.png)

## Read Test Data from CSV file in Jmeter    

- Create a CSV file in the test suite folder and add test data to it.

![createCSV](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/CSV%20DataFile/newuser-CSV-Data.png)
- Add a Config Element CSV Data Set Config in Jmeter.

![configCSV](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/CSV%20Data%20Config%20and%20Passed%20Screenshot/CSV%20Data%20Set%20Config.png)

- Configure ' CSV Data Set Config ' based on the need such as providing path of CSV file and variable names and other configs. 

![readCSV](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/CSV%20Data%20Config%20and%20Passed%20Screenshot/CSV%20File%20to%20Set%20Variable.png)

![readCSV](https://github.com/Mahmuduls1995/Performance-Testing-With-JMeter-BookingApp/blob/main/CSV%20Data%20Config%20and%20Passed%20Screenshot/Newuser-Data%20-Set-From-CSV-File.png)

- Run the test to see if data from the CSV file is read and populated in the results.  <br/>

## Test execution from GUI
 
- JMeter should be initialized in GUI mode.
- Click on Run Button.