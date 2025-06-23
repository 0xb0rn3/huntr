# huntr 🎯
*Intelligent Network Discovery Tool with Adaptive Dependency Management*

## Overview

huntr is a professional-grade network scanning tool that combines the simplicity of traditional ping sweeps with the power of modern network discovery technologies. What sets huntr apart is its intelligent dependency management system that automatically detects, installs, and configures the best available scanning tools for your system.

Rather than forcing users to manually install and configure multiple network tools, huntr creates a seamless experience that adapts to your environment and provides progressively enhanced capabilities based on what's available on your system.

## Philosophy & Design Principles

### Invisible Infrastructure
The most powerful tools are those where complexity is hidden from the user while keeping full functionality accessible. huntr embodies this philosophy by handling package management, dependency resolution, and tool configuration behind the scenes, presenting users with a clean interface that "just works."

### Progressive Enhancement
huntr starts with basic functionality that works everywhere (standard ping), then progressively offers more sophisticated options as additional tools become available. This ensures immediate value while allowing users to benefit from enhanced capabilities as their system grows.

### Graceful Degradation
When something goes wrong—whether it's missing dependencies, network issues, or insufficient privileges—huntr doesn't crash or confuse users. Instead, it clearly explains what happened and continues with whatever functionality remains available.

## Quick Start

### Installation
```bash
# Clone the repository
git clone https://github.com/0xb0rn3/huntr.git
cd huntr

# Make executable
chmod +x huntr

# Run the tool
./huntr
```

### Basic Usage
```bash
# Interactive mode (recommended for first-time users)
./huntr

# The tool will:
# 1. Check network connectivity
# 2. Detect your package manager
# 3. Install missing dependencies automatically
# 4. Present available scanning methods
# 5. Guide you through network discovery
```

## Scanning Methods Explained

huntr provides five different scanning approaches, each with distinct advantages and use cases. Understanding when to use each method will help you make informed decisions based on your specific needs.

### Method 1: Optimized Ping
**Best for**: First-time users, systems without additional tools, basic network validation
**Speed**: Moderate (30-60 seconds for /24 subnet)
**Reliability**: High
**Requirements**: None (uses system ping)

This method improves upon basic ping scanning by using aggressive timeout settings and parallel execution. While not the fastest option, it provides reliable results on any system without requiring additional software installation.

### Method 2: Batch Parallel Processing
**Best for**: Resource-constrained systems, networks with older equipment
**Speed**: Good (15-30 seconds for /24 subnet)
**Reliability**: Very High
**Requirements**: None (uses system ping)

This approach demonstrates controlled concurrency principles by processing IP addresses in manageable batches rather than overwhelming the system with hundreds of simultaneous processes. This prevents system overload while maintaining good performance.

### Method 3: nmap Discovery Scan
**Best for**: Professional network assessment, detailed host information
**Speed**: Very Good (5-15 seconds for /24 subnet)
**Reliability**: Excellent
**Requirements**: nmap (auto-installed)

nmap represents the gold standard in network discovery tools. Beyond simple connectivity testing, nmap provides sophisticated timing algorithms, adaptive behavior based on network conditions, and the foundation for more advanced network analysis.

### Method 4: fping Lightning Scan
**Best for**: Regular network monitoring, quick connectivity checks
**Speed**: Excellent (2-5 seconds for /24 subnet)
**Reliability**: Very Good
**Requirements**: fping (auto-installed)

fping was designed specifically for parallel ping operations. Unlike traditional ping that handles one host at a time, fping manages multiple network operations within a single process, dramatically reducing overhead and improving performance.

### Method 5: masscan Extreme Speed
**Best for**: Large-scale network discovery, security assessments
**Speed**: Outstanding (under 2 seconds for /24 subnet)
**Reliability**: Good (requires careful configuration)
**Requirements**: masscan (auto-installed), root privileges

masscan achieves extreme speed by implementing its own network stack and bypassing much of the operating system's networking overhead. This approach requires root privileges but can scan thousands of hosts per second.

## Technical Architecture

### Dependency Management System
huntr includes a sophisticated dependency management system that works across different Linux distributions. The system performs several key functions:

**Package Manager Detection**: Automatically identifies whether your system uses apt, yum, dnf, pacman, zypper, or apk, then adapts its installation commands accordingly.

**Network Validation**: Before attempting any installations, huntr verifies internet connectivity using multiple DNS servers to ensure reliable results.

**Silent Installation**: Package installations run silently to avoid overwhelming users with technical output, while providing clear progress indicators and status updates.

**Automatic Cleanup**: After installations complete, huntr automatically cleans package caches to prevent accumulation of unnecessary files.

### Performance Optimization Strategies
The tool implements several performance optimization strategies that demonstrate important concepts in systems programming:

**Asynchronous Processing**: Multiple network operations run simultaneously rather than sequentially, dramatically reducing total scan time.

**Resource Management**: Batch processing prevents system overload by controlling the number of concurrent operations.

**Timeout Optimization**: Aggressive timeout settings balance speed with reliability, preventing slow networks from unnecessarily extending scan times.

**Process Efficiency**: Tools like fping and masscan minimize process creation overhead by handling multiple operations within single processes.

## Supported Operating Systems

huntr works across major Linux distributions through its adaptive package management system:

- **Debian/Ubuntu**: Uses apt package manager
- **Red Hat/CentOS/Fedora**: Uses yum or dnf package manager  
- **Arch Linux**: Uses pacman package manager
- **openSUSE**: Uses zypper package manager
- **Alpine Linux**: Uses apk package manager

The tool automatically detects your distribution and uses the appropriate package management commands, ensuring consistent behavior regardless of your underlying system.

## Understanding Network Scanning Concepts

### ICMP vs TCP vs UDP Scanning
huntr primarily uses ICMP (ping) based discovery, which works by sending Internet Control Message Protocol packets to target hosts. This approach is effective for basic connectivity testing but has some limitations in environments where ICMP is filtered or blocked.

### Timing and Rate Limiting
Different scanning tools use various approaches to timing and rate limiting. Understanding these concepts helps explain why performance varies between methods:

**Conservative Timing**: Slower but more reliable, suitable for unstable networks
**Aggressive Timing**: Faster but may miss hosts on slow or congested networks  
**Adaptive Timing**: Adjusts based on network conditions and response patterns

### Parallel vs Sequential Processing
Traditional network scanning processes hosts one at a time (sequential), while modern tools process multiple hosts simultaneously (parallel). This fundamental difference explains the dramatic performance improvements you'll observe between basic ping and tools like fping or masscan.

## Advanced Usage Examples

### Scanning Different Network Sizes
```bash
# Scan a small network (Class C)
./huntr
# Enter: 192.168.1

# Scan a larger network segment  
./huntr
# Enter: 10.0.1

# Scan corporate network range
./huntr  
# Enter: 172.16.10
```

### Performance Benchmarking
To understand the performance characteristics of different methods on your specific network, try running the same scan with different methods and compare the results. You'll typically observe these performance tiers:

1. masscan: 1-3 seconds
2. fping: 2-5 seconds  
3. nmap: 5-15 seconds
4. batch parallel: 15-30 seconds
5. optimized ping: 30-60 seconds

These numbers vary based on network conditions, the number of active hosts, and system performance.

## Troubleshooting Guide

### Common Issues and Solutions

**"Permission denied" errors**: Some scanning methods require elevated privileges. Run with sudo if needed, particularly for masscan.

**"Command not found" errors**: If dependency installation fails, check your internet connection and package manager configuration.

**Slow performance**: If scans seem unusually slow, check for network congestion or try a different scanning method.

**Missing results**: Some firewalls block ICMP traffic. Consider using nmap with TCP-based discovery for more comprehensive results.

### Network Considerations
Different network environments may affect scanning results:

**Corporate Networks**: May have strict firewall rules that block scanning traffic
**Cloud Environments**: Often implement security groups that filter ICMP traffic
**Home Networks**: Usually allow ICMP but may have performance limitations on consumer hardware
**Virtual Networks**: May have additional latency that affects timing-sensitive scans

## Contributing

We welcome contributions that improve huntr's functionality, reliability, or educational value. When contributing, please consider:

**Code Quality**: Follow the existing patterns for error handling, user feedback, and cross-platform compatibility.

**Documentation**: Include clear explanations of new features and the networking concepts they demonstrate.

**Testing**: Verify functionality across different Linux distributions and network environments.

**Educational Value**: Consider how new features can help users learn networking and systems administration concepts.

## Security Considerations

Network scanning tools can be powerful, and with that power comes responsibility:

**Authorized Use Only**: Only scan networks you own or have explicit permission to test.

**Rate Limiting**: Aggressive scanning can overwhelm network equipment or trigger security systems.

**Logging Awareness**: Network scanning activities are often logged and monitored.

**Tool Selection**: Choose appropriate scanning methods based on your environment and requirements.

## License

This project is open source and available under standard open source licensing terms. Please use responsibly and in accordance with applicable laws and regulations.

## Educational Resources

To deepen your understanding of the networking concepts demonstrated in huntr, consider exploring:

**Network Protocol Fundamentals**: Understanding ICMP, TCP, and UDP protocols
**Systems Programming**: Process management, concurrency, and resource optimization  
**Linux System Administration**: Package management, user privileges, and system security
**Network Security**: Responsible disclosure, authorized testing, and security best practices

The concepts you learn through understanding and using huntr apply broadly across network administration, security assessment, and systems programming disciplines.

---

*huntr - Making network discovery accessible, educational, and powerful.*
