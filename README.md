# Distributed near-Real Time Radio Intelligence Controller (near-RT RIC)

A distributed near-RT RIC implementation featuring OpenAirInterface5G integration with multiple E2 interfaces support, Improved FlexRIC framework, and AI-driven network optimization capabilities. The 5G Core network is shared within the same repository to show all the software modules to run the end-to-end setup. 

## Architecture

![Architecture Deployment](ArchDeployment.png)

## Features

- **FlexRIC Framework**: Distributed near-RT-RIC implementation improving the OAI FlexRIC with the config files to run the banchemarks
- **AI/ML Optimization**: DQN-based load balancing and network optimization
- **OAI O-RAN Implementation**: Extended OAI RAN source code to support multiple E2AP interfaces with the config files to run the banchemarks
- **5G Core Network**: Complete OAI CN5G for the setup and have the same environment as our testbed

## Components

### Core Components
- **OpenAirInterface5G**: 5G RAN implementation with E2 agent
- **FlexRIC**: Near-real-time RIC platform
- **OAI CN5G**: 5G Core Network functions
- **DQN RIC**: AI-driven resource optimization

### Key Directories
- `openairinterface5g/`: 5G RAN with E2 interface
- `flexric_scale/`: Scalable RIC implementation
- `oai-cn5g-fed/`: 5G Core Network federation
- `DqnRic/`: Deep Q-Network based RIC optimization
- `xapp_analytics/`: Analytics and monitoring xApps

## Quick Start

### Prerequisites
- Ubuntu 20.04/22.04 or RHEL 8/9
- CMake 3.15+
- GCC 9+

### Quick build of OpenAirInterface5G with E2

```bash
cd openairinterface5g/cmake_targets
./build_oai --gNB --nrUE -w SIMU -w USRP --build-lib nrscope --build-e2 --ninja
```

For detailed installation instructions, see the [Installation Guides](#installation-guides) section below.

### Build the extended FlexRIC 

```bash
cd flexric_scale
make
./build/examples/ric/nearRT-RIC
```
For detailed installation instructions, see the [Installation Guides](#installation-guides) section below.
### Deploy 5G Core Network

```bash
cd oai-cn5g-fed/docker-compose
python3 core-network.py --type start-basic --scenario 1
```

For detailed installation instructions, see the [Installation Guides](#installation-guides) section below.

## Configuration

- **RIC Configuration**: `flexric_scale/flexric.conf`
- **E2 Agent**: Built into OAI gNB
- **Core Network**: `oai-cn5g-fed/docker-compose/`

## Installation Guides

### OpenAirInterface5G
- [Build Guide](openairinterface5g/doc/BUILD.md)
- [Run Guide](openairinterface5g/doc/RUNMODEM.md)
- [Features](openairinterface5g/doc/FEATURE_SET.md)
- [E2AP Integration](openairinterface5g/openair2/E2AP/README.md)

### FlexRIC
- [Main Installation Guide](flexric_scale/README.md)
- [Demo Guide](flexric_scale/DEMO.md)
- [Scale Demo](flexric_scale/DEMO_Scale.md)
- [Docker Deployment](flexric_scale/test/docker/README.md)

### OAI 5G Core Network
- [Main Guide](oai-cn5g-fed/README.md)
- [Home Deployment](oai-cn5g-fed/docs/DEPLOY_HOME.md)
- [Prerequisites](oai-cn5g-fed/docs/DEPLOY_PRE_REQUISITES.md)
- [Debug Guide](oai-cn5g-fed/docs/DEBUG_5G_CORE.md)

## Documentation

## License

This project combines multiple open-source components with their respective licenses. See individual component directories for specific license information.

---

© 2025 Rafik ZITOUNI
