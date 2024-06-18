# Operating System Detection from Wireshark Network Packet Trace using Various ML Models
_____

To see the full research report, see the (operatingsystemdetection.pdf) file at the root of the repository. 

_____

## Purpose:

The purpose of this research project is to train three ML models (Random Forest, MLP Classifier, and Decision Tree Classifier) on a labelled wireshark network packet trace obtained from different machines running different operating systems and versions. The models are tested and analysed, and their ability to detect the operating system from the packet trace alone is used to compare the different models.

## Project Goals:

- Pre-process and load network trace (PCAP file) using scapy library and extract needed ip / tcp headers to generate training / test data and label data based on IP address - OS mappings
- Train three models using the sci-kit learn module, namely the RandomForestClassifier, MLPClassifier, and DecisionTreeClassifier.
- Test each models and analyse their performance by computing accuracy scores, precision, recall, f1-score, and support where appropriate, and plot results. 
- Compare model performance and analyse feature importance to conclude learned patterns in OS detection.
- Fine tune data and hyperparamters and retrain best performing model to extend results and report on findings

## Dataset:

The dataset using in training should be downloaded and placed underneath the (data) directory in the root of the repository, specifically the (data/os-100-packet.pcap) file. This dataset can also be obtained from (https://drive.google.com/file/d/1hlyGHqCgxPofS0HvCCl-ToKR-XbBtuPV/view?usp=sharing) which is part of the nPrintML research project (https://nprint.github.io/benchmarks/os_detection/nprint_os_detection.html) and is originally taken from the "Intrusion detection evaluation dataset (CIC-IDS2017)" at (https://www.unb.ca/cic/datasets/ids-2017.html). 

The dataset includes 12439 traces, each trace consisting of 100 packets, that correspond to one of the following operating systems: "Ubuntu 16.4, 64B", "Win 10, pro 32B", "Win 10, 64B", "Ubuntu 16.4, 32B", "Ubuntu 14.4, 64B", "Ubuntu 14.4, 32B", "MAC", "Win 8.1, 64B", "Web server 16 Public", "Ubuntu server 12 Public", "Windows Vista", "Win 7 Pro, 64B", "Kali". The following features were disallowed in training to avoid learning irrelevant features that reveal the label via the network topology: IPv4 Source IP, IPv4 Destination IP, TCP Ssource Port, TCP Destination Port, TCP SEQ and TCP ACK Numbers.

## How to Run Project:

See the .ipynb notebook at the root of the directory, data has to be downloaded from repository or link under the dataset section and placed in a directory called ./data. 

Make sure all libraries are installed from the requirements.txt file. This can be done by running the command ```pip install -r requirements.txt```.

Notebook blocks can then be run to commence training, testing, and analysis. 
