## 关键问题
- complex, large-scale distributed systems
- thousands of machines across multiple physical facilities
- different teams, perhaps in different programming languages

## 为什么
1. the engineer may not be aware precisely which services are in use; new services and pieces may be added and modified from week to week, both to add user-visible features and to improve other aspects such as performance or security

1.  the engineer will not be an expert on the internals of every service; each one is built and maintained by a different team

1.  services and machines may be shared simultaneously by many different clients, so a performance artifact may be due to the behavior of another application

## 目标
1. Low overhead
1. Application-level transparency and cover application needs
1. Scalability
1. available for analysis quickly

## 概念
1. span - tracing tree node
1. common trace id - probabilistically unique 64-bit integers
1. additional information of high level api

##  dapper trace collection
1. span data is written  to local log files
1. pulled from all production hosts by Dapper daemons and collection in- frastructure
1. written to a cell in one of several regional Dapper Bigtable repositories