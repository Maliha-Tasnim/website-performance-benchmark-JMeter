## Overview

This project uses Apache JMeter to evaluate the performance of a website by simulating various load conditions. It includes JMeter configurations and test plans designed to measure key metrics such as response time, throughput, and error rate under specified conditions.

## Features

🔹Simulates various load scenarios, including different numbers of virtual users.

🔹Measures response times, throughput, error percentages, and other key metrics.

🔹Generates reports to help analyze the impact of load on website performance.

## Prerequisites

🔹Java Development Kit (JDK): JMeter requires Java to run. Ensure you have [JDK 8](https://www.oracle.com/java/technologies/downloads/#java11?er=221886) or above installed. 

🔹Apache JMeter: Download [JMeter](https://jmeter.apache.org/download_jmeter.cgi) from Apache JMeter's official site. 

## Functionalities

Apache JMeter is an open-source tool designed by the Apache Software Foundation for load and performance testing across various services, with a primary focus on web applications. In this project, JMeter is used to conduct load and performance testing on multiple e-commerce websites, along with REST API testing. This project evaluates the load performance of four popular e-commerce websites:

                        1. Amazon.com
                        
                        2. Aliexpress.com
                        
                        3. Flipkart.com
                        
                        4. Daraz.com.bd


Each website is tested under similar conditions to compare their load-handling capabilities. Additionally, specific pages on Amazon.com are analyzed to measure load times under varying scenarios.


### Test Configuration

For each website, the following test configuration is applied:


                        1. Thread Group (Users): 100 users

                        2. Ramp-Up Period: 5 seconds

                        3. Loop Count: 1


### Explanation of Ramp-Up Period

The ramp-up period specifies how long JMeter takes to reach the full number of threads (users). In this case:


    1. 100 threads (users) are configured to start within a 5-second ramp-up period.

    2. This means each thread begins approximately every 0.05 seconds (5 seconds / 100 threads).

    3. For example, if there are 30 threads with a 120-second ramp-up period, 
       each successive thread will start 4 seconds after the previous one.

    𝑺𝒕𝒂𝒓𝒕 𝒘𝒊𝒕𝒉 𝑹𝒂𝒎𝒑 − 𝒖𝒑 = 𝒏𝒖𝒎𝒃𝒆𝒓 𝒐𝒇 𝒕𝒉𝒓𝒆𝒂𝒅𝒔 𝒂𝒏𝒅 𝒂𝒅𝒋𝒖𝒔𝒕 𝒖𝒑 𝒐𝒓 𝒅𝒐𝒘𝒏 𝒂𝒔 𝒏𝒆𝒆𝒅𝒆𝒅

Tip: Adjusting the ramp-up period can help avoid excessive load at the start of a test while ensuring that threads start running before others complete (unless a staggered start is desired).


### Test Pages for Amazon.com

For Amazon.com, three specific pages are evaluated:


                        1. Sign In

                        2. Sign Up

                        3. Today’s Deals


These pages are analyzed individually to assess load times and response consistency under simulated user traffic.


### Assertion & Response Verification

To ensure reliable test results, Response Assertion scripts are used to verify that the tested pages are functioning as expected:

1. Response Code: A response code of 200 (OK) is expected, which indicates the page has loaded successfully.

2. Purpose: This verification confirms that the pages are available and meet basic performance criteria without necessarily validating the page content.


This approach helps identify potential issues in page loading and response times while verifying that critical web elements are accessible during the test.

### Analysis & Comparison

The project compares:

1. Intra-site performance: By analyzing load performance across different pages on Amazon.com.

2. Inter-site performance: By comparing load performance across the four e-commerce websites.

The results provide insights into each website’s scalability, responsiveness, and stability under simulated load conditions.


## Installation & Configuring Test Parameters

1. Clone this repository:  git clone https://github.com/Maliha-Tasnim/website-performance-benchmark-JMeter.git

2. Download JMeter: Extract the downloaded JMeter package and ensure it’s accessible in the system’s PATH or note its location for usage.

3. Launch Apache JMeter (run jmeter or open jmeter.bat in Windows).

4. Open the JMeter test plan (.jmx file) provided in this repository to review or modify configurations as needed.

5. Modify thread counts, ramp-up periods, and loop counts to simulate different loads.

6. Customize target URLs, test duration, and other JMeter settings as per the website's needs.


## Running Tests

1. Start the Test: Run the test by clicking the green Start button in JMeter.

2. Monitor Results: Use the View Results Tree and Summary Report listeners in JMeter to observe real-time test results.

3. Exporting Results for Analysis: JMeter allows to save results in formats such as CSV or XML, which can be used for further reporting.

