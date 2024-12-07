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
## Test Plan
Testplan > Add > Threads (Users) > Thread Group (this might vary dependent on the jMeter version you are using)
- Name: Users
- Number of Threads (users): 1, 100, 500, 1000, 2000
- Ramp-Up Period (in seconds): 10
- Loop Count: 1  

  1) The general setting for the tests execution, such as whether Thread Groups will run simultaneously or sequentially, is specified in the item called Test Plan.

  2) All HTTP Requests will use some default settings from the HTTP Request, such as the Server IP, Port Number, and Content-Encoding.

  3) Each Thread Group specifies how the HTTP Requests should be carried out. To determine how many concurrent "users" will be simulated, one must first know the number of threads. The number of actions each "user" will perform is determined by the loop count.

  4) The HTTP Header Manager, which allows you to provide the Request Headers that will be utilized by the upcoming HTTP Requests, is the first item in Thread Groups.


