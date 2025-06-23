# huntr 🥷🎯
*Intelligent Network Discovery Tool with Adaptive Dependency Management and Advanced Stealth Capabilities*

## Overview

huntr is a professional-grade network scanning tool that combines the simplicity of traditional ping sweeps with the power of modern network discovery technologies and cutting-edge stealth techniques. What sets huntr apart is its intelligent dependency management system that automatically detects, installs, and configures the best available scanning tools for your system, while providing advanced evasion capabilities for security professionals and penetration testers.

Rather than forcing users to manually install and configure multiple network tools, huntr creates a seamless experience that adapts to your environment and provides progressively enhanced capabilities based on what's available on your system. The tool now includes sophisticated stealth features that allow network reconnaissance while minimizing detection by security monitoring systems.

## Philosophy & Design Principles

### Invisible Infrastructure
The most powerful tools are those where complexity is hidden from the user while keeping full functionality accessible. huntr embodies this philosophy by handling package management, dependency resolution, and tool configuration behind the scenes, presenting users with a clean interface that "just works."

### Progressive Enhancement
huntr starts with basic functionality that works everywhere (standard ping), then progressively offers more sophisticated options as additional tools become available. This ensures immediate value while allowing users to benefit from enhanced capabilities as their system grows. The new stealth capabilities represent the pinnacle of this progressive enhancement philosophy.

### Graceful Degradation
When something goes wrong—whether it's missing dependencies, network issues, or insufficient privileges—huntr doesn't crash or confuse users. Instead, it clearly explains what happened and continues with whatever functionality remains available.

### Operational Security Focus
Network reconnaissance is a critical skill in cybersecurity, but it must be performed responsibly and with consideration for detection avoidance. huntr now provides both educational insight into how network scanning works and practical tools for conducting reconnaissance in environments where stealth is paramount.

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
# 4. Present available scanning methods (including stealth options)
# 5. Guide you through network discovery with appropriate evasion techniques
```

## Scanning Methods Explained

huntr now provides multiple scanning approaches across two operational modes: standard scanning for network administration tasks and stealth scanning for security assessment scenarios. Understanding when to use each method helps you make informed decisions based on your specific operational requirements and risk tolerance.

### Standard Scanning Methods

These methods prioritize speed and efficiency for legitimate network administration tasks where detection is not a concern.

#### Method 1: Optimized Ping
**Best for**: First-time users, systems without additional tools, basic network validation
**Speed**: Moderate (30-60 seconds for /24 subnet)
**Reliability**: High
**Detection Risk**: Moderate
**Requirements**: None (uses system ping)

This method improves upon basic ping scanning by using aggressive timeout settings and parallel execution. While not the fastest option, it provides reliable results on any system without requiring additional software installation. The scanning pattern is easily detectable by network monitoring systems due to its regular timing and sequential IP addressing.

#### Method 2: Batch Parallel Processing
**Best for**: Resource-constrained systems, networks with older equipment
**Speed**: Good (15-30 seconds for /24 subnet)
**Reliability**: Very High
**Detection Risk**: Moderate
**Requirements**: None (uses system ping)

This approach demonstrates controlled concurrency principles by processing IP addresses in manageable batches rather than overwhelming the system with hundreds of simultaneous processes. This prevents system overload while maintaining good performance, though the regular batching pattern can still be detected by sophisticated monitoring systems.

#### Method 3: nmap Discovery Scan
**Best for**: Professional network assessment, detailed host information
**Speed**: Very Good (5-15 seconds for /24 subnet)
**Reliability**: Excellent
**Detection Risk**: High (aggressive timing creates distinctive signatures)
**Requirements**: nmap (auto-installed)

nmap represents the gold standard in network discovery tools. Beyond simple connectivity testing, nmap provides sophisticated timing algorithms, adaptive behavior based on network conditions, and the foundation for more advanced network analysis. However, its default aggressive timing creates easily recognizable traffic patterns.

#### Method 4: fping Lightning Scan
**Best for**: Regular network monitoring, quick connectivity checks
**Speed**: Excellent (2-5 seconds for /24 subnet)
**Reliability**: Very Good
**Detection Risk**: High (burst traffic patterns are distinctive)
**Requirements**: fping (auto-installed)

fping was designed specifically for parallel ping operations. Unlike traditional ping that handles one host at a time, fping manages multiple network operations within a single process, dramatically reducing overhead and improving performance. The rapid-fire packet transmission creates a distinctive "burst" signature easily identified by intrusion detection systems.

#### Method 5: masscan Extreme Speed
**Best for**: Large-scale network discovery, security assessments
**Speed**: Outstanding (under 2 seconds for /24 subnet)
**Reliability**: Good (requires careful configuration)
**Detection Risk**: Very High (floods network with traffic)
**Requirements**: masscan (auto-installed), root privileges

masscan achieves extreme speed by implementing its own network stack and bypassing much of the operating system's networking overhead. This approach requires root privileges but can scan thousands of hosts per second. The massive traffic volume makes it nearly impossible to hide from network monitoring systems.

### Stealth Scanning Methods

These methods prioritize detection avoidance through sophisticated evasion techniques, accepting reduced speed as the cost of operational security.

#### Method 1: Stealth Ping Sweep
**Best for**: Initial reconnaissance in monitored environments
**Speed**: Slow (2-5 minutes for /24 subnet)
**Reliability**: High
**Detection Risk**: Very Low
**Evasion Techniques**: Randomized timing, packet fragmentation, TTL variation, randomized IP order

This method transforms basic ping scanning into a sophisticated reconnaissance tool by introducing multiple layers of evasion. Random delays between probes (0.1-0.5 seconds) prevent timing-based detection, while packet fragmentation and TTL randomization make individual packets appear to come from different sources or network paths. The randomized IP scanning order prevents sequential pattern recognition.

#### Method 2: Ultra-Stealth nmap
**Best for**: Professional penetration testing, advanced reconnaissance
**Speed**: Very Slow (5-10 minutes for /24 subnet)
**Reliability**: Excellent
**Detection Risk**: Low
**Evasion Techniques**: Decoy IPs, MAC address spoofing, packet fragmentation, randomized timing, source port randomization

This method leverages nmap's advanced evasion capabilities to create sophisticated camouflage. Decoy IP addresses make it appear that multiple sources are conducting the scan simultaneously, while MAC address spoofing and source port randomization further obscure the true origin. The combination of these techniques creates traffic that blends with normal network activity.

#### Method 3: Stealth fping
**Best for**: Ongoing monitoring in security-conscious environments
**Speed**: Slow (2-4 minutes for /24 subnet)
**Reliability**: Very Good
**Detection Risk**: Low
**Evasion Techniques**: Controlled timing intervals, randomized target order, graduated packet intervals

This approach transforms fping's parallel capabilities into a stealth reconnaissance tool by implementing controlled timing intervals and randomized target selection. Instead of flooding the network with simultaneous probes, it carefully spaces requests to mimic normal network traffic patterns while maintaining reasonable performance.

#### Method 4: Stealth masscan
**Best for**: Large-scale stealth reconnaissance
**Speed**: Moderate (30-60 seconds for /24 subnet)
**Reliability**: Good
**Detection Risk**: Low
**Evasion Techniques**: Ultra-low packet rates, source port randomization, randomized host order

This method dramatically reduces masscan's packet rate from thousands per second to approximately 50 per second, spreading the scan over a much longer time period to avoid detection. Source port randomization and randomized host order further disguise the systematic nature of the reconnaissance.

## Technical Architecture

### Dependency Management System
huntr includes a sophisticated dependency management system that works across different Linux distributions. The system performs several key functions while maintaining operational security considerations.

**Package Manager Detection**: Automatically identifies whether your system uses apt, yum, dnf, pacman, zypper, or apk, then adapts its installation commands accordingly. This ensures that stealth tools like nmap, fping, and masscan are available regardless of your distribution.

**Network Validation**: Before attempting any installations, huntr verifies internet connectivity using multiple DNS servers to ensure reliable results. This validation process uses discrete queries that don't reveal the tool's intended purpose.

**Silent Installation**: Package installations run silently to avoid overwhelming users with technical output, while providing clear progress indicators and status updates. This approach also prevents sensitive information about installed tools from appearing in system logs unnecessarily.

**Automatic Cleanup**: After installations complete, huntr automatically cleans package caches to prevent accumulation of unnecessary files that might indicate the presence of reconnaissance tools.

### Stealth Architecture Components

The stealth functionality is built around several key architectural principles that demonstrate advanced concepts in network security and evasion techniques.

**Timing Randomization Engine**: A sophisticated random delay generator that creates unpredictable intervals between network probes. This system uses multiple randomization sources to prevent pattern recognition by adaptive security systems.

**Packet Manipulation Framework**: Low-level packet crafting capabilities that modify various packet characteristics including Time-To-Live values, packet sizes, and fragmentation patterns. These modifications make reconnaissance traffic appear to originate from different network paths and sources.

**Decoy Generation System**: Intelligent creation of believable decoy IP addresses that participate in scanning activities, making it difficult for defenders to identify the true source of reconnaissance. The system avoids common network addresses and creates realistic traffic patterns for each decoy.

**Traffic Pattern Camouflage**: Algorithms that analyze normal network traffic characteristics and adjust scanning behavior to blend with legitimate network activity. This includes mimicking typical user behavior patterns and avoiding signatures that security tools commonly detect.

### Performance Optimization Strategies

The tool implements several performance optimization strategies that demonstrate important concepts in systems programming while maintaining stealth capabilities.

**Asynchronous Processing**: Multiple network operations run simultaneously rather than sequentially, dramatically reducing total scan time even when stealth delays are introduced.

**Resource Management**: Intelligent batch processing prevents system overload by controlling the number of concurrent operations, while ensuring that resource usage patterns don't create distinctive signatures.

**Adaptive Timeout Optimization**: Dynamic timeout adjustment based on network conditions and stealth requirements, balancing speed with reliability and detection avoidance.

**Memory-Efficient Target Management**: Efficient handling of large target lists using streaming algorithms that minimize memory footprint and avoid creating distinctive system resource usage patterns.

## Understanding Network Evasion Concepts

Network reconnaissance evasion is a complex field that combines understanding of network protocols, monitoring systems, and human behavior patterns. huntr provides practical insight into these concepts through its stealth implementations.

### Timing-Based Evasion

Traditional network scanning creates distinctive timing signatures that security systems can easily detect. Consistent intervals between probes, regular packet sizes, and sequential target selection all create patterns that stand out from normal network traffic.

**Random Interval Generation**: True stealth requires unpredictable timing that mimics human behavior or natural network fluctuations. huntr implements sophisticated randomization that avoids both regular patterns and obviously artificial randomness.

**Burst Avoidance**: Many scanning tools create traffic "bursts" that are easily detected. Stealth scanning spreads activity over time to avoid creating distinctive traffic volume patterns.

**Long-Term Pattern Disruption**: Advanced monitoring systems look for patterns across extended time periods. huntr includes techniques for breaking long-term patterns through strategic pauses and timing variation.

### Packet-Level Evasion

Modern network security systems analyze individual packets for signs of scanning activity. Effective evasion requires understanding how these systems work and implementing countermeasures at the packet level.

**Fragmentation Techniques**: Breaking packets into fragments can bypass security systems that don't properly reassemble fragmented traffic. huntr implements intelligent fragmentation that appears natural while evading detection.

**TTL Manipulation**: Time-To-Live values can reveal information about packet origins and network paths. By varying TTL values, reconnaissance traffic can appear to come from different network locations.

**Protocol Characteristic Randomization**: Varying packet sizes, timing, and other characteristics prevents the creation of distinctive protocol signatures that security tools can identify.

### Source Obscuration

Hiding the true source of reconnaissance traffic is crucial for operational security. huntr implements several techniques for source obscuration that demonstrate advanced networking concepts.

**Decoy IP Strategy**: By making scanning traffic appear to come from multiple sources, it becomes difficult for defenders to identify the true origin of reconnaissance activity. Effective decoy selection requires understanding network topology and typical traffic patterns.

**MAC Address Spoofing**: At the data link layer, changing the apparent hardware address can prevent tracking across network segments and avoid hardware-based identification.

**Source Port Randomization**: Using unpredictable source ports prevents port-based tracking and makes traffic appear more like normal user activity.

## Operational Security Considerations

Network reconnaissance carries significant operational security implications that responsible practitioners must understand and address.

### Legal and Ethical Framework

Network scanning activities exist within a complex legal and ethical framework that varies by jurisdiction and context. Understanding these boundaries is crucial for responsible practice.

**Authorized Testing Only**: Network scanning should only be performed on networks you own or have explicit written permission to test. Unauthorized scanning can violate computer crime laws and result in serious legal consequences.

**Scope Limitation**: Even when authorized, scanning activities should be limited to the specific scope agreed upon with network owners. Exceeding authorized scope can transform legitimate testing into unauthorized access.

**Data Handling**: Information gathered during reconnaissance activities may be sensitive and should be handled according to established security protocols and legal requirements.

### Detection Risk Assessment

Understanding detection risks helps practitioners choose appropriate techniques for their operational environment and risk tolerance.

**Network Monitoring Capabilities**: Different environments have varying levels of network monitoring sophistication. Corporate networks typically have more advanced monitoring than home networks, requiring different evasion approaches.

**Traffic Analysis Systems**: Some organizations employ advanced traffic analysis systems that can detect subtle patterns in network activity. Understanding these capabilities helps inform technique selection.

**Response Procedures**: Organizations may have automated or manual response procedures for detected scanning activity. Understanding potential responses helps in planning reconnaissance activities.

### Operational Planning

Effective reconnaissance requires careful planning that considers technical, legal, and operational factors.

**Target Environment Assessment**: Understanding the target environment's likely monitoring capabilities, network architecture, and security posture informs technique selection and timing decisions.

**Timeline Planning**: Stealth reconnaissance often requires extended time periods to avoid detection. Planning activities around business hours, maintenance windows, and other operational factors can improve success rates.

**Contingency Planning**: Having plans for various scenarios, including detection or technical failures, ensures that reconnaissance activities can be conducted safely and effectively.

## Supported Operating Systems

huntr works across major Linux distributions through its adaptive package management system, ensuring that both standard and stealth capabilities are available regardless of your underlying platform.

- **Debian/Ubuntu**: Uses apt package manager for tool installation
- **Red Hat/CentOS/Fedora**: Uses yum or dnf package manager
- **Arch Linux**: Uses pacman package manager
- **openSUSE**: Uses zypper package manager
- **Alpine Linux**: Uses apk package manager

The tool automatically detects your distribution and uses the appropriate package management commands, ensuring consistent behavior and stealth capability availability regardless of your underlying system.

## Advanced Usage Examples

### Stealth Reconnaissance Scenarios

Understanding when and how to use different stealth techniques helps maximize operational effectiveness while minimizing detection risk.

#### Corporate Network Assessment
```bash
# Initial stealth reconnaissance of corporate network
./huntr
# Select stealth ping sweep for initial discovery
# Enter: 192.168.1
# Follow up with ultra-stealth nmap for detailed analysis of discovered hosts
```

#### Penetration Testing Scenarios
```bash
# Multi-phase reconnaissance approach
./huntr
# Phase 1: Use stealth masscan for broad network discovery
# Phase 2: Use ultra-stealth nmap for detailed host analysis
# Phase 3: Use stealth fping for ongoing monitoring
```

#### Long-Term Monitoring
```bash
# Establish ongoing stealth monitoring
./huntr
# Use stealth fping with extended timing for regular network monitoring
# Vary timing patterns to avoid long-term detection
```

### Performance vs Stealth Trade-offs

Understanding the relationship between scanning speed and detection risk helps in making informed operational decisions.

**Maximum Stealth (2-10 minutes per /24 subnet)**: Ultra-stealth nmap, stealth ping sweep
**Balanced Approach (30-120 seconds per /24 subnet)**: Stealth fping, stealth masscan
**Speed-Optimized (2-60 seconds per /24 subnet)**: Standard methods with operational security awareness

These timing estimates vary significantly based on network conditions, target responsiveness, and stealth configuration parameters.

## Troubleshooting Guide

### Common Stealth-Related Issues

**Slow Performance**: Stealth techniques inherently trade speed for detection avoidance. If performance is too slow, consider adjusting timing parameters or using less aggressive stealth techniques.

**Incomplete Results**: Some stealth techniques may miss hosts that respond slowly or have strict filtering. Consider using multiple stealth approaches or adjusting timeout values.

**Permission Requirements**: Advanced stealth techniques may require elevated privileges for packet manipulation or raw socket access. Use sudo when prompted for maximum capability.

**Network Compatibility**: Some network configurations may interfere with advanced stealth techniques. If problems occur, try different stealth methods or fall back to standard scanning approaches.

### Detection Troubleshooting

**Suspected Detection**: If you suspect your reconnaissance has been detected, immediately cease scanning activity and assess the situation. Consider whether to continue with more aggressive stealth techniques or abort the activity.

**False Positive Reduction**: Some stealth techniques may trigger false positives in sensitive security environments. Adjust timing parameters or use different evasion approaches to reduce false positive rates.

**Monitoring System Analysis**: Understanding how your reconnaissance appears to monitoring systems can help refine techniques and improve future operational effectiveness.

## Educational Resources

Network reconnaissance and evasion represent complex fields that combine technical knowledge with operational awareness. Developing expertise requires understanding both the technical mechanisms and the broader context in which they operate.

**Network Protocol Analysis**: Deep understanding of TCP/IP, ICMP, and other network protocols provides the foundation for effective reconnaissance and evasion techniques.

**Security Monitoring Systems**: Understanding how intrusion detection systems, network monitoring tools, and security information and event management platforms work helps in developing effective evasion strategies.

**Operational Security Principles**: Learning operational security concepts from military and intelligence contexts provides valuable insight into conducting reconnaissance activities safely and effectively.

**Legal and Ethical Framework**: Understanding the legal and ethical implications of network reconnaissance helps ensure that activities remain within appropriate boundaries.

**Practical Application**: Hands-on experience with different network environments, monitoring systems, and evasion techniques builds the practical skills necessary for effective reconnaissance.

## Contributing

Contributions that enhance huntr's educational value, operational effectiveness, or technical capabilities are welcome. When contributing, please consider both the technical merit and the educational impact of proposed changes.

**Code Quality**: Follow established patterns for error handling, user feedback, cross-platform compatibility, and operational security considerations.

**Documentation**: Provide clear explanations of new features, the networking concepts they demonstrate, and their operational security implications.

**Testing**: Verify functionality across different Linux distributions, network environments, and operational scenarios.

**Educational Value**: Consider how new features help users understand networking, reconnaissance, and operational security concepts.

**Responsible Disclosure**: Ensure that contributions maintain the tool's focus on authorized testing and responsible security research.

## Security and Legal Considerations

Network reconnaissance tools provide powerful capabilities that must be used responsibly and within appropriate legal and ethical boundaries.

**Authorization Requirements**: Only use huntr on networks you own or have explicit written permission to test. Unauthorized network scanning can violate computer crime laws and result in serious legal consequences.

**Scope Compliance**: Limit activities to the specific scope authorized by network owners. Exceeding authorized scope can transform legitimate testing into unauthorized access.

**Detection Awareness**: Understand that even stealth techniques may be detected by sophisticated monitoring systems. Plan activities with appropriate operational security measures.

**Data Protection**: Handle information gathered during reconnaissance activities according to established security protocols and legal requirements.

**Professional Responsibility**: Use reconnaissance capabilities only for legitimate security testing, research, or educational purposes. Avoid activities that could harm systems or compromise user privacy.

## License

This project is open source and available under standard open source licensing terms. Please use responsibly, within legal boundaries, and in accordance with applicable laws and regulations.

---

*huntr - Making network discovery accessible, educational, and operationally secure for authorized security professionals.*

**Stealth Capabilities**: Advanced evasion techniques for professional reconnaissance
**Educational Focus**: Learn networking and operational security concepts through practical application
**Responsible Use**: Designed for authorized testing and legitimate security research
