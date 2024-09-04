# Hacker-USB


![Hacker-USB](https://github.com/user-attachments/assets/39250907-8f81-4d89-b182-1f6f36148a8c)

## USB pen drive as like : USB Rubber Ducky

---

# USB Pen Drive AutoRun Script for Penetration Testing and Ethical Hacking

This repository contains a customizable USB pen drive autorun script designed for ethical hacking and penetration testing tasks. This script can be used to automatically execute a variety of tools or payloads upon insertion of the USB drive, enabling rapid deployment of tests or the collection of information.

## Features

- **Automated Payload Execution**: Automatically runs specified scripts or tools when the USB is plugged in.
- **Customizable Payloads**: Easily configure the script to execute different tools or commands depending on the testing requirements.
- **Stealthy Operations**: Designed for quick and discreet deployment, ideal for social engineering and physical security assessments.
- **Cross-Platform Capabilities**: Supports Windows, with potential adaptations for Linux and macOS.

## Requirements

- USB pen drive
- Basic knowledge of scripting (e.g., Bash, PowerShell, Batch)
- Familiarity with penetration testing tools and techniques

## Getting Started

### Windows

1. **Create Your Payload**:
   - Write a `.bat` or `.ps1` file containing the penetration testing commands or scripts you wish to execute automatically.
   - Example `.bat` file to collect basic system info:
     ```batch
     @echo off
     systeminfo > %TEMP%\sysinfo.txt
     ipconfig /all >> %TEMP%\sysinfo.txt
     ```

2. **Create an Autorun.inf File**:
   - Place an `autorun.inf` file in the root of the USB drive with the following content:
     ```ini
     [Autorun]
     open=payload.bat
     action=Execute Payload
     icon=myicon.ico
     ```
   - Replace `payload.bat` with the name of your script, and optionally set a custom icon for the USB drive.

3. **Save and Test**:
   - Place both the `autorun.inf` and your payload script in the root directory of the USB drive.
   - Insert the USB drive into the target system to test the autorun functionality.

   > **Note**: Autorun is disabled by default on most modern versions of Windows for security reasons. To enable it, manual intervention may be necessary, and this is generally not recommended outside controlled environments.

### Linux & macOS

1. **Create a Shell Script**:
   - Write a `.sh` script to perform your desired penetration testing tasks.
   - Example `.sh` file to list active connections:
     ```bash
     #!/bin/bash
     netstat -an > /tmp/netstat.txt
     ```

2. **Configure Autorun via udev Rules (Linux)** or **Launch Agents (macOS)**:
   - **Linux**: Create a udev rule that triggers the script when the USB is inserted.
   - **macOS**: Use a Launch Agent to execute the script automatically when the USB is mounted.

3. **Deploy**:
   - Place the script on the USB drive and set up the necessary rules or agents on the target system to trigger the script execution.

## Ethical Usage

This script is intended strictly for use in authorized penetration testing engagements and security assessments. Unauthorized use of this tool to access or compromise systems without permission is illegal and unethical.

## Customization

- **Modify Payloads**: Adapt the script to execute different penetration testing tools, such as Metasploit payloads, reverse shells, or data collection utilities.
- **Add Logging**: Configure the script to log actions or results to a remote server or a hidden directory on the USB drive for later analysis.
- **Targeted Execution**: Customize the script to run specific payloads based on the target system's environment (e.g., OS detection).

## Security Considerations

- **Handling Autorun Safely**: Ensure that the script is tested in a controlled environment before deploying in real-world scenarios.
- **Avoiding Detection**: Be mindful of antivirus and endpoint protection systems that may flag autorun scripts as malicious.

## Disclaimer

This tool is provided for educational and ethical hacking purposes only. The author is not responsible for any misuse or damage caused by this tool. Always obtain proper authorization before conducting penetration testing or deploying scripts on systems you do not own.

## Contributing

Contributions to improve this tool are welcome. Please fork the repository, make your improvements, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This README emphasizes the ethical use of the tool, provides clear instructions for setting up autorun payloads, and outlines customization options for penetration testing tasks. Make sure to adjust any specific details to match your project requirements.
