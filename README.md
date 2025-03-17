# BlazeDemo Performance Testing with JMeter & BlazeMeter

## Overview
This project showcases performance testing of the BlazeDemo website using **Apache JMeter** and **BlazeMeter**. The test simulates users searching for flights and proceeding with dummy purchases to measure performance under load.

## Tools & Technologies Used
- **Apache JMeter** (Test creation and execution)
- **BlazeMeter Chrome Extension** (Script recording)
- **BlazeDemo** (Demo website for performance testing)

## Test Scenario
1. **Recording:** Used BlazeMeter Chrome Extension to record a test flow:
   - Navigate to [BlazeDemo](https://www.blazedemo.com/)
   - Search for a flight (Departure: Paris, Destination: Buenos Aires)
   - Select a flight and proceed to checkout
   - Fill in dummy passenger details and submit

2. **Execution:**
   - Loaded the recorded **.jmx** file in JMeter
   - Configured 100 users with a ramp-up time of 10 seconds
   - Used multiple listeners to monitor and analyze performance:
     - **Summary Report**
     - **Aggregate Report**
     - **View Results Tree**
     - **View Results in Table**

## Project Files
| File | Description |
|------|-------------|
| `BlazeDemo.jmx` | JMeter test script |
| `aggregate.csv` | Aggregate report (Performance statistics) |
| `summary.csv` | Summary report (Key metrics) |

## How to Run the Test
1. **Install JMeter:** Download and install [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi).
2. **Load the JMX file:**
   - Open JMeter
   - Click **File > Open** and select `BlazeDemo.jmx`
3. **Run the test:** Click the **Start** button (Green Play icon) in JMeter.
4. **View Results:** Open listeners (Summary Report, Aggregate Report) to analyze test performance.

## Key Performance Metrics
- **Throughput:** The number of requests handled per second.
- **Response Time:** Time taken for requests to complete.
- **Error Rate:** Percentage of failed requests.
- **Concurrent Users:** The number of simulated users interacting with the system.
**Key Metrics (Aggregate Report)**
| Label                 | Samples | Average (ms) | 90% Line (ms) | Throughput (req/sec) | Error % |
|-----------------------|---------|--------------|---------------|----------------------|---------|
| Homepage              | 100     | 590          | 613           | 9.54                 | 0%      |
| Flight Search         | 100     | 394          | 429           | 9.92                 | 0%      |
| Flight Purchase       | 100     | 393          | 419           | 9.88                 | 0%      |
| Purchase Confirmation | 100     | 588          | 611           | 9.71                 | 0%      |
| **TOTAL**             | 800     | 491          | 599           | 9.34                 | 0%      |

## Findings & Observations
- The server handled **100 concurrent users** efficiently with minimal response time degradation.
- No significant errors were encountered during execution.
- The test helped evaluate BlazeDemo's capability under simulated load conditions.

## Future Enhancements
- Increase the user load to assess scalability.
- Implement distributed load testing using multiple JMeter instances.
- Integrate with **BlazeMeter** cloud for advanced reporting.

## Author
**Muhammad Asad Nabeel Yousaf**

Feel free to contribute, suggest improvements, or use this project as a reference for your performance testing needs!
