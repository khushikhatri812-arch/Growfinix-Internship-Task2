# Phishing-Simulation-Campaign

A complete, end-to-end phishing simulation campaign environment using *GoPhish* and *MailHog*. This project was developed to understand security awareness workflows, email tracking, and credential capturing in a controlled local environment.

---

## Overview
This repository contains the documentation and configuration details for a phishing simulation exercise. The goal was to build a functional pipeline that simulates a real-world phishing attack, allowing for the analysis of user interaction metrics like email opens, link clicks, and credential submissions.

##  Tech Stack
*   *GoPhish*: Open-source phishing framework used for campaign orchestration.
*   *MailHog*: Email testing tool used as a local SMTP server to capture outgoing campaign emails.
*   *Local Environment*: All components are deployed on localhost (127.0.0.1) for safe, isolated testing.

##  Key Components

### 1. SMTP Sending Profile
Configured GoPhish to route outgoing emails through MailHog for testing purposes.
*   *Host*: 127.0.0.1:1025
*   *Encryption*: None (Local test environment)

### 2. Campaign Setup
*   *Campaign Name*: C1
*   *Template*: Designed to simulate an urgent "Action Required" data update.
*   *Landing Page*: Created a custom login page (TourEnquiries Portal2) to capture and log mock credential submissions.

##  Tracking & Metrics
This simulation successfully validates the following metrics tracked by GoPhish:
*   *Email Opened*: Verified via tracking pixel integration.
*   *Link Clicked*: Validated using unique tracking URLs per user.
*   *Data Submitted*: Confirmed that mock credentials are captured and logged upon form submission on the landing page.

##  Troubleshooting & Challenges

During the setup of this campaign, I encountered a few challenges. Below are the problems faced and how they were resolved:

### 1. Incorrect Landing Page URL
*   *Problem*: Initially, I used http://192.168.1.1 as the landing page URL, which is a router IP and caused the campaign links to fail.
*   *Resolution*: Updated the URL field to http://127.0.0.1 (localhost) to ensure the landing page was correctly reachable within the local testing environment.

### 2. URL Field Formatting Errors
*   *Problem*: I accidentally included extra brackets and repeated text in the URL input field, which broke the link structure.
*   *Resolution*: Cleaned the input field to contain only the direct URL (http://127.0.0.1), ensuring the generated links in the emails were formatted correctly.

### 3. Campaign Status Monitoring
*   *Problem*: Initially, I was unsure when the campaign was actually "live" and ready for testing.
*   *Resolution*: Monitored the GoPhish dashboard until the campaign status transitioned from "In progress" to "Completed," ensuring the emails had been successfully dispatched to the MailHog server.

##  Conclusion
The end-to-end workflow is fully functional. This project serves as a practical demonstration of how security awareness platforms track vulnerabilities in a simulated environment.
