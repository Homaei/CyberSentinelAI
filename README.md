# Log Analysis and Anomaly Detection System

This repository contains the implementation of an integrated log analysis and anomaly detection system using Zabbix, Wazuh, and a large language model (LLM). The system is designed to collect, preprocess, and analyze logs from network devices and servers to detect potential security threats. 

## System Overview 

The system leverages Zabbix and Wazuh for log collection, Elasticsearch for log aggregation and storage, and advanced machine learning models for anomaly detection. It categorizes alerts into various severity levels and automates responses based on predefined criteria.

## Components

- **Zabbix**: Used for collecting network and server performance logs.
- **Wazuh**: Focuses on security monitoring, collecting logs from various endpoints.
- **Elasticsearch**: Aggregates and stores logs from Zabbix and Wazuh.
- **Logstash/Fluentd**: Used for preprocessing logs, including normalization and noise reduction.
- **TensorFlow/PyTorch**: Frameworks for training the machine learning model to detect anomalies.
- **Docker/Kubernetes**: For deploying the system components in a scalable and manageable way.
- **ELK Stack**: Used for real-time monitoring and visualization.
- **StackStorm/Rundeck**: Automation tools for handling alerts and responses based on severity.


## LLM/AI stages:
- **Feature Extraction**: Collect and preprocess data from network devices via Zabbix proxies, organizing it into structured summaries. Craft detailed text prompts that are ready for analysis by the LLM.
- **Anomaly Detection**: Analyze the preprocessed data using the LLM to identify deviations from standard operational patterns. Utilize specific prompts that guide the LLM's focus during analysis.
- **Threat Assessment**: Use the LLM to assess the severity of detected anomalies, evaluating their potential impact on network security and operational stability. Generate prompts that ask the LLM to evaluate threat severity.
- **Solution Generation**: Generate actionable mitigation strategies tailored to address specific security risks based on the severity of the threats identified. Employ prompts that instruct the LLM to propose particular solutions.
- **Output-Actionable Advice**: Communicate the LLM's recommendations to the Zabbix Server to trigger automated scripts or alert administrators for further action. Use prompts to transform LLM outputs into direct, executable actions or clear advisory notifications.

## Architecture

Below is the high-level architecture of the system:

![Architecture Diagram](./CyberDiagram.webp)

```plaintext


```

```plaintext
Internet
  ├── Firewall 1
  │     ├── Zabbix/Wazuh Proxy 1
  │     │     ├── Office 1
  │     │     │     ├── Switch
  │     │     │     │     ├── WiFi
  │     │     │     │     ├── LAN
  │     │     │     │     └── NAS
  │     │     │     └── Data sent to Zabbix/Wazuh Server
  │     │     └── Connected to AWS/Azure Cloud (VPS with Zabbix/Wazuh Server)
  │
  ├── Firewall 2
  │     ├── Zabbix/Wazuh Proxy 2
  │     │     ├── Office 2
  │     │     │     ├── Switch
  │     │     │     │     ├── WiFi
  │     │     │     │     ├── LAN
  │     │     │     │     └── NAS
  │     │     │     └── Data sent to Zabbix/Wazuh Server
  │     │     └── Connected to AWS/Azure Cloud (VPS with Zabbix/Wazuh Server)
  │
  ├── Zabbix/Wazuh Proxy 3
  │     ├── Raspberry Pi
  │     │     ├── Water Treatment Plant
  │     │     │     ├── PLCs (Programmable Logic Controllers)
  │     │     │     └── SCADA (Supervisory Control and Data Acquisition)
  │     │     └── Data sent to Zabbix/Wazuh Server
  │
  └── Zabbix/Wazuh Server (AWS/Azure Cloud)
        ├── Feature Extraction (LLM/AI Solution)
        │     ├── Collects and preprocesses data from Zabbix/Wazuh logs
        │     ├── Organizes data into structured summaries
        │     └── Prepares data for analysis by the LLM
        │
        ├── Anomaly Detection (LLM/AI Solution)
        │     ├── Uses LLM to analyze preprocessed data
        │     ├── Identifies deviations from normal operational patterns
        │     └── Employs specific prompts to guide analysis
        │
        ├── Threat Assessment (LLM/AI Solution)
        │     ├── Evaluates severity of detected anomalies
        │     ├── Considers potential impacts on network security and operations
        │     └── Generates prompts to assess the threat severity
        │
        ├── Solution Generation (LLM/AI Solution)
        │     ├── Proposes actionable solutions based on threat severity
        │     ├── Recommends strategies tailored to specific security issues
        │     └── Uses prompts to instruct the LLM to provide mitigation actions
        │
        └── Output/Actionable Advice (LLM/AI Solution)
              ├── Communicates recommendations to Zabbix for automated scripts
              ├── Alert administrators for further action
              └── Displays actionable advice and notifications

```
## Contributors

- [Hubert Homaei](https://github.com/homaei), [Aagustin di Bartolo](https://github.com/Jacklamotta) , and [Oscar Mogollon](https://github.com/omogollo2).
  


## 📚 How to Cite a Part of This Research

If you use this work in your research, please cite it using one of the following formats:

---

### 📌 APA (7th Edition)

**arXiv version**:  
Homaei, M., Di Bartolo, A., Mogollón-Gutiérrez, Ó., Broncano Morgado, F., & García Rodríguez, P. (2025). *A virtual cybersecurity department for securing digital twins in water distribution systems*. arXiv. https://doi.org/10.48550/arXiv.2504.20266

---

### 📌 IEEE

**arXiv version**:  
M. Homaei, A. Di Bartolo, Ó. Mogollón-Gutiérrez, F. Broncano Morgado, and P. García Rodríguez, “A virtual cybersecurity department for securing digital twins in water distribution systems,” *arXiv*, 2025. [Online]. Available: https://doi.org/10.48550/arXiv.2504.20266

---

### 📌 Chicago (Author-Date)

**arXiv version**:  
Homaei, MohammadHossein, Agustín Di Bartolo, Óscar Mogollón-Gutiérrez, Fernando Broncano Morgado, and Pablo García Rodríguez. 2025. *A Virtual Cybersecurity Department for Securing Digital Twins in Water Distribution Systems*. arXiv. https://doi.org/10.48550/arXiv.2504.20266


### 📌 BibTeX

```bibtex
@misc{homaei2025virtual,
  author       = {Homaei, Mohammadhossein and Di Bartolo, Agustin and Mogollon-Gutierrez, Oscar and Broncano Morgado, Fernando and Garcia Rodriguez, Pablo},
  title        = {A Virtual Cybersecurity Department for Securing Digital Twins in Water Distribution Systems},
  year         = {2025},
  publisher    = {arXiv},
  doi          = {10.48550/arXiv.2504.20266},
  url          = {https://arxiv.org/abs/2504.20266},
  note         = {arXiv preprint arXiv:2504.20266},
  keywords     = {Cryptography and Security (cs.CR), Machine Learning (cs.LG), Networking and Internet Architecture (cs.NI)}
}
```
---
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
