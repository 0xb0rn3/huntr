# 🥷 Huntr

[![Version](https://img.shields.io/badge/version-0.1.2-blue.svg)](https://github.com/0xb0rn3/huntr/releases)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS-lightgrey.svg)](#compatibility)
[![Bash](https://img.shields.io/badge/bash-4.0%2B-orange.svg)](#requirements)

> Advanced Network Discovery & Reconnaissance Tool with Intelligent Filtering

Huntr is a powerful bash-based network reconnaissance tool that combines stealth scanning capabilities with intelligent filtering and comprehensive service enumeration. Built for penetration testers, security researchers, and network administrators.

## ✨ Features

### 🔍 **Core Capabilities**
- **Ultra-Stealth Scanning** - Advanced evasion with decoys, packet fragmentation, and timing randomization
- **Intelligent Host Discovery** - Enhanced nmap integration with XML parsing and smart filtering
- **Automated Service Enumeration** - Comprehensive port scanning with service detection
- **Web Application Fingerprinting** - HTTP/HTTPS service analysis and technology detection

### 🛡️ **Advanced Features (v6module)**
- **IPv6 + IPv4 Dual-Stack** - Complete network coverage
- **Vulnerability Assessment** - Automated security testing
- **SMB/NetBIOS Enumeration** - Windows network analysis
- **Database Service Discovery** - SQL server detection
- **IoT Device Discovery** - Embedded and smart device identification
- **Topology Mapping** - Network structure visualization

### 🚀 **System Integration**
- **Auto-Update System** - Seamless version management
- **System-Wide Installation** - Install once, use anywhere
- **Dependency Management** - Automatic tool installation
- **Enhanced Reporting** - Detailed scan results and exports

## 🎯 Quick Start

### One-Line Installation
```bash
curl -s https://raw.githubusercontent.com/0xb0rn3/huntr/main/install.sh | bash
```

### Manual Installation
```bash
# Clone the repository
git clone https://github.com/0xb0rn3/huntr.git
cd huntr

# Make executable
chmod +x huntr

# Run interactive mode
./huntr
```

### System-Wide Installation
```bash
# Install globally (requires sudo)
./huntr --install-system

# Now use from anywhere
huntr
```

## 📋 Requirements

### Core Dependencies
- **bash** 4.0+
- **nmap** (auto-installed)
- **curl** (for updates)

### Optional Tools (Auto-Installed)
- **fping** - Fast ping utility
- **masscan** - High-speed port scanner
- **hping3** - Advanced ping utility
- **bc** - Mathematical calculations
- **xmllint** - Enhanced XML parsing

### Supported Systems
- 🐧 **Linux** (Ubuntu, Debian, CentOS, Arch, etc.)
- 🍎 **macOS** (with Homebrew)
- 🐳 **Docker** containers
- ☁️ **Cloud instances** (AWS, GCP, Azure)

## 🎮 Usage

### Interactive Mode
```bash
# Start interactive menu
./huntr

# Example network input
Enter network base: 192.168.1
```

### Command Line Options
```bash
./huntr --help              # Show help
./huntr --version           # Show version
./huntr --update            # Update to latest version
./huntr --check-update      # Check for updates only
./huntr --install-system    # Install system-wide
./huntr --uninstall-system  # Remove system installation
./huntr --system-status     # Show installation status
```

## 🎯 Scanning Methods

### 1. 🥷 Ultra-Stealth Scan
Advanced evasion techniques for penetration testing:
- Decoy IP generation
- Packet fragmentation (-f)
- MAC address spoofing
- Timing randomization
- Random data lengths

### 2. ⚡ Fast Optimized Scan
Speed-optimized discovery for network administration:
- Parallel processing
- Intelligent timeouts
- Multi-probe discovery
- Enhanced XML parsing

### 3. 🔍 Comprehensive Scans
Combined host discovery + port enumeration:
- Service detection
- Banner grabbing
- Common port identification
- Stealth or fast variants

### 4-17. 🌐 Enhanced Features (v6module)
Advanced reconnaissance capabilities:
- **IPv6 scanning** - Complete dual-stack coverage
- **Web enumeration** - HTTP service analysis
- **SMB discovery** - Windows network mapping
- **Database detection** - SQL server identification
- **Ultimate recon** - All techniques combined

## 🛠️ Configuration

### Stealth Mode Settings
```bash
# Timing and evasion parameters
STEALTH_MODE=false
RANDOMIZE_ORDER=true
DECOY_COUNT=3
MIN_DELAY=0.1
MAX_DELAY=0.5
```

### Nmap Optimization
```bash
# Performance tuning
NMAP_PARALLEL_MIN=10
NMAP_PARALLEL_MAX=50
NMAP_HOST_TIMEOUT="3s"
NMAP_DISCOVERY_PROBES=4
```

### Advanced Configuration (v6module)
```bash
# Load enhanced features
source .v6module

# Custom scanning parameters
configure_v6_settings
```

## 📊 Example Output

```bash
🎯 Using advanced nmap host discovery with intelligent filtering...
⚡ FAST MODE: Optimized for speed and efficiency
Discovery method: -PE -PA80,443,22,21,25,53,135,139,445
Timing template: T4

📋 Active hosts discovered:
----------------------------------------
🎯 192.168.1.1 (router.local)
🎯 192.168.1.10 (desktop-pc.local)
🎯 192.168.1.25
🎯 192.168.1.45 (printer.local)
----------------------------------------
📊 Scan Summary:
• Active hosts found: 4
• Scan duration: 12s
• Average time per host: 0.05s
• Optimization: Parallel processing, smart timeouts, multi-probe discovery
```

## 🔄 Update Management

### Automatic Updates
Huntr includes an intelligent update system:

```bash
# Check for updates
./huntr --check-update

# Update to latest version
./huntr --update

# Force update check on startup
./huntr  # Automatic silent check
```

### Version Comparison
- Semantic versioning support
- Pre-release version handling
- Development version detection
- Rollback capability with backups

## 🏗️ Architecture

### File Structure
```
huntr/
├── huntr                 # Main executable
├── .v6module            # Enhanced features module
├── install.sh           # Installation script
├── README.md           # Documentation
└── examples/           # Usage examples
```

### System Paths
```bash
# System-wide installation
/usr/local/bin/huntr           # Main executable
/etc/huntr/.v6module          # System configuration
~/.config/huntr/              # User settings

# Local installation
./huntr                       # Main executable
./.v6module                  # Local configuration
```

## 🔧 Troubleshooting

### Common Issues

**Permission Denied**
```bash
chmod +x huntr
```

**Missing Dependencies**
```bash
# Dependencies auto-install on first run
./huntr  # Will detect and install missing tools
```

**Network Connectivity**
```bash
# Test network access
ping -c 1 8.8.8.8

# Check firewall settings
sudo ufw status
```

**Update Failures**
```bash
# Manual update
curl -O https://raw.githubusercontent.com/0xb0rn3/huntr/main/huntr
chmod +x huntr
```

### Debug Mode
```bash
# Enable verbose output
bash -x ./huntr
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md).

### Development Setup
```bash
# Fork and clone
git clone https://github.com/yourusername/huntr.git
cd huntr

# Create feature branch
git checkout -b feature/amazing-feature

# Make changes and test
./huntr --version

# Submit pull request
```

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **nmap** team for the incredible scanning engine
- **fping** developers for fast ICMP capabilities
- **masscan** project for high-speed scanning
- Security community for testing and feedback

## 📞 Contact & Support

- **Developer**: 0xb0rn3 | 0xbv1
- **Instagram**: [@theehiv3](https://instagram.com/theehiv3)
- **GitHub**: [0xb0rn3/huntr](https://github.com/0xb0rn3/huntr)
- **Issues**: [GitHub Issues](https://github.com/0xb0rn3/huntr/issues)

## ⚖️ Legal Disclaimer

This tool is intended for legitimate security testing and network administration purposes only. Users are responsible for ensuring compliance with all applicable laws and regulations. The developers assume no liability for misuse of this tool.

---

<div align="center">

**🥷 Huntr v0.1.2** - Advanced Network Discovery & Reconnaissance Tool

Made with ❤️ by [0xb0rn3](https://github.com/0xb0rn3)

</div>
