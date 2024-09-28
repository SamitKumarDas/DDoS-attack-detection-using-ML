
# Network Service Attack Detection in Software Defined Networking

This project aims to detect Distributed Denial of Service (DDoS) attacks in Software Defined Networking (SDN) environments using machine learning techniques. It leverages the flexibility and programmability of SDN to create a real-time DDoS detection mechanism while minimizing controller involvement.

## Project Overview
Distributed Denial-of-Service (DDoS) attacks pose a significant threat to network security, especially in SDN environments where controllers can become points of failure. This project utilizes various machine learning classifiers to detect DDoS attacks, compares their performance, and integrates them with SDN controllers for real-time attack mitigation.

### Key Features
- **Machine Learning Models**: The project implements multiple ML classifiers, including Random Forest, SVM, K-Nearest Neighbors (KNN), Decision Trees, and Naive Bayes, to detect DDoS attacks.
- **Feature Selection**: Uses filter, wrapper, and embedded methods to select the optimal subset of features for attack detection, improving accuracy and reducing computational cost.
- **DDoS Attack Types**: Detects various DDoS attacks, including ICMP Flood, SYN Flood, UDP Flood, and Smurf Attack.
- **Integration with SDN**: Employs the RYU controller and Mininet to simulate network topologies and generate traffic, including both legitimate and DDoS traffic.

## Project Structure
- **controller/**: Contains the Python scripts used for collecting traffic data and implementing the DDoS detection logic on the RYU controller.
  - `DT_controller.py`, `KNN_controller.py`, `RF_controller.py`: Implement different machine learning models on the controller.
  - `collect_benign_trafic.py`, `collect_ddos_trafic.py`: Scripts for collecting legitimate and DDoS traffic respectively.

- **mininet/**: Scripts for generating network traffic in Mininet.
  - `generate_benign_trafic.py`: Generates legitimate network traffic.
  - `generate_ddos_trafic.py`: Simulates DDoS attacks.

- **ml/**: Contains the machine learning models for classifying traffic.
  - `DT.py`, `KNN.py`, `RF.py`, `SVM.py`: Machine learning models for traffic classification.

## Setup and Requirements

### Prerequisites
- Python 3.x
- RYU SDN Framework
- Mininet Network Emulator
- Required Python libraries: `numpy`, `pandas`, `scikit-learn`, `matplotlib`, `seaborn`

### Installation
1. Install the required Python packages:
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn
   ```

2. Install [RYU](https://ryu.readthedocs.io/en/latest/getting_started.html) and [Mininet](http://mininet.org/download/).

3. Clone the repository:
   ```bash
   git clone https://github.com/your-username/sdn-network-ddos-detection.git
   cd sdn-network-ddos-detection
   ```

## Usage
1. **Start Mininet**: Set up a network topology using Mininet and generate traffic.
   ```bash
   sudo mn --topo linear,3 --controller remote --switch ovsk --mac --arp
   ```

2. **Run the RYU Controller**: Execute the desired DDoS detection model on the RYU controller.
   ```bash
   ryu-manager controller/RF_controller.py
   ```

3. **Generate Traffic**: Use the scripts in the `mininet/` folder to generate normal and DDoS traffic.
   ```bash
   python3 mininet/generate_benign_trafic.py
   python3 mininet/generate_ddos_trafic.py
   ```

4. **Evaluate ML Models**: Run the machine learning models to classify traffic and detect DDoS attacks.
   ```bash
   python3 ml/RF.py
   ```

## Results
- The project compares the performance of various machine learning algorithms, with Random Forest achieving the highest accuracy of **99.97%** on selected features.
- The real-time detection model was successfully implemented and tested in a virtual network using Mininet, achieving reliable detection of ICMP Flood, SYN Flood, UDP Flood, and Smurf Attack.

## Future Work
- Extend the detection to other types of attacks such as Smurf, Probe, R2L, and U2R in a multi-controller environment.
- Enhance the scalability of the detection mechanism in larger SDN architectures.
