## What is performance testing?
Is a non-functional testing approach to ensure that the application and the isolated elements of it will perform well under expected workload.
## What is JMeter?
JMeter is an open-source Java-based tool primarily used for performance testing web applications. 

# Content

- [Load testing Report]()  
- [Summary]()  
- [Introduction]()  

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


