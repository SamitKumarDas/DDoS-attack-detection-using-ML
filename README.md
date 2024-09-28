
# Detection of DDoS Attacks in Software-Defined Networking (SDN)

This project focuses on identifying Distributed Denial of Service (DDoS) attacks in Software-Defined Networking (SDN) using various machine learning techniques. Leveraging SDN’s unique architecture, the goal is to create a dynamic detection system that can identify and mitigate network threats in real-time.

## Overview
In an SDN environment, the controller can become a critical point of failure if attacked. This project uses machine learning algorithms to detect DDoS attacks and integrates them into SDN for live detection and response. By examining traffic patterns and identifying anomalies, this system aims to enhance network security and reduce the impact of potential attacks.

### Key Features
- **Machine Learning Models**: Various algorithms are employed to classify and detect malicious traffic.
- **Feature Optimization**: By utilizing feature selection techniques, we narrow down the dataset to the most relevant attributes, which improves detection accuracy and reduces processing time.
- **Multiple Attack Detection**: The project can identify multiple types of DDoS attacks, ensuring broad protection against potential threats.
- **Integration with SDN**: Real-world network topologies are simulated, allowing for practical testing in a virtualized SDN environment.

## Project Structure
The project is organized into different sections that handle traffic generation, data collection, and machine learning classification. It employs an SDN controller to oversee traffic flow and monitor for anomalies. A separate component handles generating both normal and malicious network traffic for testing purposes.

## Requirements
To run the project, ensure you have the following installed:
- **Python**: Version 3.x
- **Mininet**: Network emulator for SDN
- **RYU**: Controller for managing SDN traffic
- **Python Libraries**: 
  - numpy
  - pandas
  - scikit-learn
  - matplotlib
  - seaborn

## Installation Steps
1. Clone the repository and navigate to the project folder.
2. Install the required Python libraries:
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn
   ```
3. Set up the Mininet network and start the RYU controller to begin monitoring traffic.
4. Generate normal and DDoS traffic using the built-in scripts and analyze the performance of the detection model.

## Running the Project

1. **Start the Mininet Topology**: Create a network environment for traffic generation and control.
2. **Run the Controller**: The SDN controller will monitor traffic and apply machine learning to detect DDoS attacks.
3. **Generate Traffic**: Simulate normal and attack traffic to evaluate how well the detection system works.
4. **Analyze Results**: Test the machine learning models and observe their effectiveness in identifying attack patterns.

## Results
Through testing, we found that our machine learning models achieved high accuracy in detecting DDoS attacks. The feature optimization process was crucial in improving detection speed and lowering false positive rates. Overall, the system successfully identified and mitigated attack traffic with minimal false alarms.

## Future Improvements
Looking ahead, we aim to expand the project to detect other forms of attacks and scale it to work with more complex SDN topologies. We also plan to refine the machine learning models to further enhance accuracy and reduce computational overhead.
