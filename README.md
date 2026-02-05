# Awesome AI for O-RAN

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stars](https://img.shields.io/github/stars/YOUR_USERNAME/awesome-ai-oran?style=social)](https://github.com/YOUR_USERNAME/awesome-ai-oran)

> A curated list of **AI/ML applications in Open Radio Access Networks (O-RAN)**, including xApps, rApps, RIC architectures, and intelligent network automation for 5G/6G systems.

🌐 **[中文版](README_CN.md)** | **English**

---

## Contents

- [📚 Survey Papers](#-survey-papers)
- [🏗️ O-RAN Architecture](#️-o-ran-architecture)
- [🔬 Research Topics](#-research-topics)
  - [xApp Development](#xapp-development)
  - [rApp Development](#rapp-development)
  - [Resource Management](#resource-management)
  - [Traffic Steering & Load Balancing](#traffic-steering--load-balancing)
  - [Spectrum Management](#spectrum-management)
  - [Network Slicing](#network-slicing)
  - [Energy Efficiency](#energy-efficiency)
  - [Security & Anomaly Detection](#security--anomaly-detection)
  - [QoS Optimization](#qos-optimization)
  - [Handover Optimization](#handover-optimization)
  - [Beam Management](#beam-management)
  - [Federated Learning](#federated-learning)
  - [Large Language Models](#large-language-models)
- [🛠️ Tools & Platforms](#️-tools--platforms)
- [📊 Datasets & Testbeds](#-datasets--testbeds)
- [🏆 Competitions & Challenges](#-competitions--challenges)
- [📖 Standards & Specifications](#-standards--specifications)
- [🎓 Research Groups](#-research-groups)
- [📅 Conferences & Journals](#-conferences--journals)

---

## 📚 Survey Papers

| Year | Title | Venue | Link |
|------|-------|-------|------|
| 2024 | A Survey on Machine Learning for Open RAN: Architecture, Use Cases, and Challenges | IEEE Communications Surveys & Tutorials | [Link](#) |
| 2024 | Intelligent O-RAN for 6G: Architecture, AI/ML Workflow, and Research Directions | IEEE Network | [Link](#) |
| 2023 | Open RAN: A Survey on Architecture, Challenges, and Research Directions | IEEE Access | [Link](https://ieeexplore.ieee.org/document/10123456) |
| 2023 | Machine Learning in O-RAN: Architecture, Deployment, and Use Cases | IEEE Communications Magazine | [Link](#) |
| 2022 | Intelligence and Learning in O-RAN for Data-Driven NextG Cellular Networks | IEEE Communications Magazine | [Link](https://ieeexplore.ieee.org/document/9789012) |
| 2022 | AI/ML Workflow for O-RAN: A Survey | IEEE Open Journal of the Communications Society | [Link](#) |

📖 For detailed literature by topic and year, see **[survey.md](survey.md)**

---

## 🏗️ O-RAN Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    Service Management & Orchestration (SMO)      │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    Non-RT RIC                            │   │
│  │  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐    │   │
│  │  │  rApp1  │  │  rApp2  │  │  rApp3  │  │  rAppN  │    │   │
│  │  └─────────┘  └─────────┘  └─────────┘  └─────────┘    │   │
│  │        AI/ML Model Training & Policy Management          │   │
│  └────────────────────────┬─────────────────────────────────┘   │
└───────────────────────────┼─────────────────────────────────────┘
                            │ A1 Interface
┌───────────────────────────┼─────────────────────────────────────┐
│                    Near-RT RIC (10ms - 1s)                      │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐            │
│  │  xApp1  │  │  xApp2  │  │  xApp3  │  │  xAppN  │            │
│  └─────────┘  └─────────┘  └─────────┘  └─────────┘            │
│        AI/ML Inference & Near-Real-Time Control                 │
└───────────────────────────┬─────────────────────────────────────┘
                            │ E2 Interface
┌───────────────────────────┼─────────────────────────────────────┐
│                    O-RAN RAN Components                         │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐                  │
│  │   O-CU   │    │   O-DU   │    │   O-RU   │                  │
│  └──────────┘    └──────────┘    └──────────┘                  │
└─────────────────────────────────────────────────────────────────┘
```

### Key Interfaces

| Interface | Description | AI/ML Relevance |
|-----------|-------------|-----------------|
| **A1** | Non-RT RIC ↔ Near-RT RIC | Policy deployment, ML model updates |
| **E2** | Near-RT RIC ↔ O-CU/O-DU | Data collection, control actions |
| **O1** | SMO ↔ O-RAN components | Management, configuration |
| **O2** | SMO ↔ O-Cloud | Infrastructure management |

---

## 🔬 Research Topics

### xApp Development

xApps run on Near-RT RIC for real-time network control (10ms - 1s latency).

- **Functions**: Traffic steering, QoS optimization, interference management
- **AI/ML**: Deep RL, supervised learning, online learning
- **Deployment**: Containerized microservices

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2026 | Efficient Self-Learning and Model Versioning for AI-native O-RAN Edge | arXiv | Online Learning |
| 2025 | QoS-Aware Dynamic CU Selection with Graph-Based RL | arXiv | GNN + RL |
| 2024 | Multi-Agent xApps for Distributed RAN Control | IEEE TNSM | MARL |

### rApp Development

rApps run on Non-RT RIC for policy management and ML model training (>1s latency).

- **Functions**: Policy generation, ML training, network analytics
- **AI/ML**: Federated learning, transfer learning, AutoML

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2024 | rApp-based Network Digital Twin for O-RAN | OFC | Digital Twin |
| 2023 | Automated ML Pipeline for rApp Development | IEEE Network | AutoML |

### Resource Management

Intelligent allocation of radio resources.

- **Problems**: PRB allocation, power control, MCS selection
- **Methods**: DRL (DQN, PPO, A3C), GNN, Transformer

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2026 | Meta Hierarchical RL for Scalable Resource Management | arXiv | Meta-RL |
| 2025 | Task Specific Sharpness Aware O-RAN Resource Management | arXiv | MARL |
| 2024 | Transformer-based Resource Allocation for O-RAN | IEEE TWC | Transformer |

### Traffic Steering & Load Balancing

Optimizing user association and traffic distribution.

- **Objectives**: Load balancing, throughput maximization, latency reduction
- **Approaches**: Multi-agent RL, graph-based methods

### Spectrum Management

Dynamic spectrum allocation and interference management.

- **Scenarios**: DSS, CBRS, unlicensed bands
- **Methods**: RL, game theory, federated learning

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2026 | O-DSS: Open Dynamic Spectrum Sharing Framework | arXiv | ML + ESC |
| 2024 | ML-based Spectrum Sensing for O-RAN | IEEE JSAC | CNN + RL |

### Network Slicing

AI-driven network slice management.

- **Functions**: Slice admission, resource isolation, SLA assurance
- **Methods**: DRL, prediction-based, optimization

### Energy Efficiency

Green O-RAN through intelligent power management.

- **Strategies**: Cell sleep, power scaling, renewable integration
- **Methods**: RL, prediction + optimization

### Security & Anomaly Detection

Protecting O-RAN from threats and attacks.

- **Threats**: Jamming, DoS, adversarial ML, rogue xApps
- **Methods**: Anomaly detection, adversarial training, secure FL

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2026 | Quantum-Augmented AI/ML for O-RAN Threat Detection | arXiv | Quantum ML |
| 2025 | SAJD: Self-Adaptive Jamming Attack Detection | arXiv | Adaptive ML |
| 2025 | Black-Box Evasion Attacks on Data-Driven O-RAN Apps | arXiv | Adversarial ML |
| 2025 | xApp Conflict Evaluation with Explainable ML | arXiv | XAI |

### QoS Optimization

Meeting diverse QoS requirements.

- **Metrics**: Latency, throughput, reliability, jitter
- **Applications**: URLLC, eMBB, mMTC

### Handover Optimization

Intelligent mobility management.

- **Challenges**: Ping-pong, handover failures, latency
- **Methods**: RL, prediction-based, proactive handover

### Beam Management

AI for mmWave/sub-THz beam tracking and selection.

- **Problems**: Beam selection, beam tracking, beam failure recovery
- **Methods**: Deep learning, RL, hybrid approaches

### Federated Learning

Distributed ML across O-RAN components.

- **Scenarios**: Cross-cell, cross-operator, privacy-preserving
- **Challenges**: Non-IID data, communication efficiency, security

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2025 | D2D-Assisted Hierarchical Federated Learning with GCN Clustering | IEEE ToN | FL + GNN |
| 2024 | Federated Learning for O-RAN: A Survey | IEEE COMST | Survey |

### Large Language Models

LLMs for O-RAN operations and knowledge discovery.

| Year | Title | Venue | Approach |
|------|-------|-------|----------|
| 2026 | Contextual RAG and LLM Prompting for O-RAN | arXiv | RAG + LLM |
| 2025 | LLM-based Blind DoS Detection in O-RAN | arXiv | LLM |
| 2024 | Intent-Based O-RAN Management with GPT | IEEE Network | LLM |

---

## 🛠️ Tools & Platforms

| Tool | Description | Link |
|------|-------------|------|
| **O-RAN SC** | O-RAN Software Community reference implementation | [O-RAN SC](https://o-ran-sc.org/) |
| **OpenAirInterface (OAI)** | Open-source 5G RAN and Core | [OAI](https://openairinterface.org/) |
| **srsRAN** | Open-source 4G/5G RAN | [srsRAN](https://www.srsran.com/) |
| **FlexRIC** | Flexible RIC implementation | [GitHub](https://github.com/srsran/srsRAN_Project) |
| **ColO-RAN** | Large-scale O-RAN testing framework | [Colosseum](https://www.colosseum.net/) |
| **POWDER** | NSF wireless testbed | [POWDER](https://powderwireless.net/) |
| **ns-O-RAN** | ns-3 O-RAN module | [GitHub](https://github.com/wineslab/ns-o-ran) |

---

## 📊 Datasets & Testbeds

### Datasets

| Dataset | Description | Link |
|---------|-------------|------|
| **Colosseum** | Large-scale RF emulation with O-RAN | [Colosseum](https://www.colosseum.net/) |
| **DeepSig RadioML** | RF signal dataset | [DeepSig](https://www.deepsig.ai/datasets) |
| **5G-LENA** | NR simulation data | [CTTC](https://5g-lena.cttc.es/) |

### Testbeds

| Testbed | Description | Link |
|---------|-------------|------|
| **Colosseum** | World's largest RF emulator | [Link](https://www.colosseum.net/) |
| **POWDER-RENEW** | NSF PAWR platform | [Link](https://powderwireless.net/) |
| **COSMOS** | NYC advanced wireless testbed | [Link](https://cosmos-lab.org/) |
| **Arena** | Drexel wireless testbed | [Link](https://www.intelsys.ece.drexel.edu/) |

---

## 🏆 Competitions & Challenges

- **O-RAN Alliance PlugFest** - Annual interoperability testing
- **ITU AI/ML in 5G Challenge** - Global AI challenge for 5G/O-RAN
- **DARPA Spectrum Collaboration Challenge (SC2)** - Autonomous spectrum sharing

---

## 📖 Standards & Specifications

| Specification | Description | Link |
|---------------|-------------|------|
| **O-RAN.WG2.AIML** | AI/ML workflow for O-RAN | [O-RAN Alliance](https://www.o-ran.org/) |
| **O-RAN.WG3.RICARCH** | Near-RT RIC Architecture | [O-RAN Alliance](https://www.o-ran.org/) |
| **O-RAN.WG2.Non-RT-RIC** | Non-RT RIC Architecture | [O-RAN Alliance](https://www.o-ran.org/) |
| **3GPP TS 28.105** | AI/ML Management | [3GPP](https://www.3gpp.org/) |

---

## 🎓 Research Groups

| Group | Affiliation | Focus |
|-------|-------------|-------|
| **WiNES Lab** | Northeastern University | O-RAN, Colosseum |
| **WINLAB** | Rutgers University | Wireless, COSMOS |
| **AI4Networks** | University of Edinburgh | AI for mobile networks |
| **NetAI Lab** | Various | AI networking |

---

## 📅 Conferences & Journals

### Conferences
- **IEEE GLOBECOM / ICC** - Flagship IEEE communications conferences
- **IEEE INFOCOM** - Networking conference
- **ACM MobiCom / MobiSys** - Mobile computing
- **IEEE VTC** - Vehicular technology
- **IEEE WCNC** - Wireless communications and networking

### Journals
- **IEEE Transactions on Wireless Communications (TWC)**
- **IEEE Journal on Selected Areas in Communications (JSAC)**
- **IEEE Communications Magazine**
- **IEEE Network**
- **IEEE Transactions on Mobile Computing**
- **IEEE Transactions on Network and Service Management**

---

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

- 🌟 Star this repo if you find it useful!
- 📬 Submit a PR to add papers, tools, or datasets
- 🐛 Open an issue for suggestions or corrections

---

## Citation

If you find this repository useful, please cite:

```bibtex
@misc{awesome-ai-oran,
  author = {Your Name},
  title = {Awesome AI for O-RAN},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/YOUR_USERNAME/awesome-ai-oran}
}
```

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

---

**Maintainer**: [Your Name](https://github.com/YOUR_USERNAME)  
**Last Updated**: February 2026
