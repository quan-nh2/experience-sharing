# Experience Sharing: Nguyen Hoang Quan

**Role**: Software Engineer  
**Years of Experience**: 5+ years  
**Relevant Areas**: E-commerce, Logistics, Finance

In this document, I will share my experience working on an automation solution for a top personal care company in Vietnam, focusing on the challenges of synchronizing stock and order data across multiple eCommerce platforms and ERP systems.

## Table of Contents
1. [Introduction](#introduction)
2. [Context and Background](#context-and-background)
3. [Problem faced](#problem-faced)
4. [Solution and Approach](#solution-and-approach)
5. [Outcome and Impact](#outcome-and-impact)
6. [Lessons Learned](#lessons-learned)
7. [Conclusion](#conclusion)

## Introduction

## Context and Background

**Project Name**: Automate support manage Ecommerce platforms.
**Team Size**: 1.
**Duration**: 1 month.

I was responsible for developing an automated solution for a leading personal care company in Vietnam to manage operations across five eCommerce websites and synchronize them with the client’s ERP system. The key requirement was to ensure seamless communication and data synchronization between the eCommerce platforms and the ERP system, specifically with regard to stock management and order processing.
The daily workflow included:
* Multiple SKUs per website: Each SKU belonged to two warehouses.
* Daily stock uploads: At 6 AM, the client uploaded stock data into a shared FSTP folder.
* Manual process: The Person in Charge (PIC) had to download the stock data, aggregate it, and manually import it into all five eCommerce websites to ensure stock updates by the start of the day.
* Reconciliation: After updating stocks, the PIC created a reconciliation report comparing the stock levels on the website with the inbound stock file and sent the report to the client’s General Manager.
* Order reporting: At 12 PM, the PIC manually generated order reports in .xlsx format for each eCommerce website and sent them via email. The client’s ERP system processed these reports to update the order statuses.


## Problem faced

The main challenges encountered in this manual process were:

* Human errors: The PIC sometimes missed critical tasks such as uploading stock data, sending reconciliation reports, or generating order reports. This led to discrepancies in stock levels or missed orders, which directly impacted business operations.

* Scalability: As the client considered expanding their operations (adding more websites or warehouses), the manual process became increasingly time-consuming and error-prone. Scaling up using the current method would drastically increase the workload and require significant resources to maintain accuracy.

## Solution and Approach

To centralize and manage data, I created an internal platform that captured all product and order information from the eCommerce platforms. 
The platform utilized the respective APIs to pull the data, ensuring that we had a consistent, up-to-date view of product stock levels and order statuses across all websites.
This platform served as the single source of truth, allowing us to not only track stock and order information more reliably but also to automate subsequent processes like reconciliation and reporting.

![pulling-ecom-information](https://github.com/quan-nh2/experience-sharing/public/images/pulling_ecom_information.png)

1. Automating Stock updates:
* Create a background job that automatically download the stock data from the FSTP folder every day at 6 AM. The background job will aggregated the stock information and pushed updates to all 5 eCommerce websitre via their respective APIs.

2. Automating Reconciliation Reports:
* With all data centralized on the internal platform, I automated the reconciliation process. The platform compared the stock data across the websites with the inbound stock files, ensuring consistency. The reconciliation report was then generated automatically using the Google Sheets API and sent to the client’s General Manager via email.

3. Automate Order Reporting:
* Using the internal platform’s centralized order data, I automated the generation of .xlsx order reports for each eCommerce website. The reports were created at 12 PM each day and automatically emailed to the client’s ERP system, ensuring timely and accurate order processing without human intervention.

### The Solution Trade-off:
 The initial development time for building the internal platform was longer than simply automating the existing manual processes, but it provided a scalable and centralized solution that minimized future errors and allowed for easy expansion.


## Outcome and Impact
The automated solution delivered several key benefits:
* 100% reduction in manual errors: The automation eliminated human errors associated with manual stock updates and order reporting.
* Increased efficiency: Tasks that previously required several hours each day were completed automatically in under 30 minutes.
* Scalability: The solution was designed to scale easily, allowing the client to add more websites and warehouses without significantly increasing workload.
* Improved accuracy: Daily reconciliation reports ensured that stock data across all platforms was always up to date, minimizing discrepancies.
Client feedback was highly positive, as the solution allowed the business to streamline their operations, freeing up resources for other critical tasks.

## Lessons Learned
* Automation is key: By automating repetitive manual tasks, we drastically improved the efficiency and accuracy of the business processes. This experience reinforced the importance of finding the right tools to streamline operations.
* Integration complexities: Working with multiple eCommerce platforms and their APIs introduced challenges in terms of data consistency and communication between systems, which required careful planning.
* Scalability: Designing systems with future scalability in mind is critical, especially for growing businesses. Building a flexible architecture early on ensured the solution could accommodate future growth.

## Conclusion

This project was a rewarding experience in automating complex workflows for eCommerce businesses. The solution not only resolved the immediate pain points of manual errors and scalability but also set the foundation for future growth. I look forward to applying similar automation strategies in future projects to optimize business operations.










