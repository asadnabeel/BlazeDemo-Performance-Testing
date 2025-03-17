# BlazeDemo Performance Testing Project

## Project Overview
A performance testing project for [BlazeDemo.com](https://www.blazedemo.com/) using Apache JMeter and BlazeMeter. The test simulates 100 users searching and purchasing flights with a ramp-up time of 10 seconds.

### Tools Used
- **Apache JMeter**: For test scripting and execution
- **BlazeMeter Extension**: For recording user flows
- **Listeners**: Summary Report, Aggregate Report, View Results Tree

## Test Scenario
1. **User Flow**:
   - Access homepage
   - Search for flights (`/reserve.php`)
   - Select flight (`/purchase.php`)
   - Confirm purchase (`/confirmation.php`)

2. **Test Configuration**:
   - Threads (Users): 100
   - Ramp-Up Period: 10 seconds
   - Loop Count: 1
   - Duration: ~90 seconds

## Key Metrics (Summary)(aggregate report)
| Label                 | Samples | Avg (ms) | Throughput (req/sec) | Error % |
|-----------------------|---------|----------|----------------------|---------|
| Homepage              | 100     | 590      | 9.54                 | 0%      |
| Flight Search         | 100     | 394      | 9.92                 | 0%      |
| Flight Purchase       | 100     | 393      | 9.88                 | 0%      |
| Confirmation Page     | 100     | 588      | 9.71                 | 0%      |

## How to Run
1. **Prerequisites**:
   - Install [JMeter](https://jmeter.apache.org/download_jmeter.cgi)
   - Java 8+ installed

2. **Steps**:
   - Clone this repository.
   - Open `BlazeDemo-Performance-Testing.jmx` in JMeter.
   - Update thread count or ramp-up time if needed.
   - Run the test plan.
   - View results in the `results/` folder.

## Files in Repository
- `test-plans/BlazeDemo-Performance-Testing.jmx`: JMeter test plan
- `results/aggregate.csv`: Aggregate report data
- `results/summary.csv`: Summary report data

## Conclusion
- All transactions completed with **0% errors**.
- Average response time: **491 ms** across all requests.
- System handled **9.34 req/sec** under 100 users.
