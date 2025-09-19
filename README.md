# Network Traffic Anomaly Detection Exercise

## Overview
Create a command-line tool that analyzes a large dataset of network traffic logs to identify potential security anomalies and suspicious patterns.

## Exercise Requirements

### Data Processing
- You'll be provided with a 2GB dataset containing millions of simulated network traffic logs in JSON format
- Each log entry contains: timestamp, source IP, destination IP, port, protocol, bytes transferred, connection duration, and user agent

### Core Requirements
1. **Data Parsing & Analysis**:
   - Process the entire dataset efficiently
   - Implement memory-efficient strategies (the dataset won't fit in memory)
   - Identify patterns of suspicious activity

2. **Anomaly Detection**:
   - Implement at least 3 different anomaly detection algorithms
   - Examples: unusual traffic spikes, suspicious port scanning, unusual geographic access patterns

3. **Performance Optimization**:
   - Tool should process the dataset in under 5 minutes on a standard laptop
   - Include benchmarking to demonstrate performance

4. **Reporting**:
   - Generate a summary report of findings
   - Prioritize anomalies by risk level
   - Include visualization data (CSV output that could be graphed)

## Technical Requirements
- Include tests for your core logic
- Provide documentation on how to run the tool
- Include a README explaining your approach and design decisions

## Sample Data Structure
Each log entry follows this JSON format:
```json
{
  "timestamp": "2025-09-19T14:30:45.123Z",
  "source_ip": "192.168.1.100",
  "destination_ip": "10.0.0.50",
  "source_port": 49152,
  "destination_port": 443,
  "protocol": "TCP",
  "bytes_transferred": 2048,
  "connection_duration_ms": 150,
  "user_agent": "Mozilla/5.0...",
  "response_code": 200,
  "country_code": "US"
}
```

## Anomaly Detection Algorithms to Implement

### 1. Port Scanning Detection
- Identify sources attempting connections to multiple ports on the same destination
- Flag sources connecting to more than 10 ports within a 60-second window

### 2. Traffic Volume Anomalies
- Detect unusual spikes in bytes transferred
- Use statistical analysis (standard deviation) to identify outliers

### 3. Geographic Anomalies
- Flag connections from unusual geographic locations
- Identify rapid geographic movements that are physically impossible

### 4. Time-based Anomalies (Bonus)
- Detect unusual activity during off-hours
- Identify patterns that deviate from historical baselines

## Expected Output

### Summary Report
```
Network Traffic Anomaly Detection Report
Generated: 2025-09-19 14:30:45 UTC
Dataset: 2.1GB, 5,234,567 log entries processed in 3m 45s

SUMMARY
=======
High Risk Anomalies: 23
Medium Risk Anomalies: 156
Low Risk Anomalies: 1,204

TOP FINDINGS
============
1. [HIGH] Port scanning from 10.1.2.3 - 47 ports scanned in 45 seconds
2. [HIGH] Impossible geographic movement - IP 203.45.67.89 (US to CN in 2 minutes)
3. [MEDIUM] Traffic spike from 192.168.1.50 - 500MB in 30 seconds (10x normal)

RECOMMENDATIONS
===============
- Investigate source IPs flagged for port scanning
- Review geographic anomaly IPs for potential VPN/proxy usage
- Monitor traffic spike sources for potential data exfiltration
```

### CSV Output for Visualization
```csv
anomaly_type,timestamp,source_ip,risk_level,details
port_scan,2025-09-19T14:25:30Z,10.1.2.3,HIGH,"47 ports scanned"
traffic_spike,2025-09-19T14:28:15Z,192.168.1.50,MEDIUM,"500MB in 30s"
geo_anomaly,2025-09-19T14:30:00Z,203.45.67.89,HIGH,"US to CN in 2min"
```

## Performance Requirements
- **Memory Usage**: Tool should not exceed 512MB RAM usage
- **Processing Time**: Complete analysis within 5 minutes
- **Accuracy**: At least 90% accuracy on provided test cases

## Evaluation Criteria

### Code Quality (40%)
- Clean, readable Ruby code
- Proper error handling and edge cases
- Effective use of Ruby idioms and patterns
- Modular design with separation of concerns

### Algorithm Efficiency (30%)
- Memory-efficient processing of large datasets
- Optimized algorithms for anomaly detection
- Proper use of data structures and indexing
- Performance benchmarking and optimization

### Detection Accuracy (20%)
- Effectiveness of anomaly detection algorithms
- Low false positive rates
- Meaningful risk prioritization
- Insightful pattern recognition

### Documentation & Usability (10%)
- Clear setup and usage instructions
- Well-documented code and design decisions
- Comprehensive test coverage
- Professional presentation of results

## Getting Started

## Deliverables
- Complete application with source code
- Test suite demonstrating functionality
- Generated sample reports showing findings
- README with setup instructions and design decisions
- Performance benchmarks and optimization notes

## Success Criteria
A successful submission will:
- Process the full 2GB dataset efficiently
- Identify meaningful security anomalies with low false positives
- Generate actionable reports for security teams
- Demonstrate strong programming skills
- Show understanding of cybersecurity concepts and data analysis

---

*This exercise simulates real-world cybersecurity challenges involving large-scale data analysis and anomaly detection, skills critical for protecting network infrastructure at enterprise scale.*
