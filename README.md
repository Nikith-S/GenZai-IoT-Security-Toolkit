
# GenZai IoT Security Toolkit

**GenZai IoT Security Toolkit** is a comprehensive tool designed to identify and address vulnerabilities in IoT devices. It enables the scanning of target URLs to detect IoT devices, assesses vendor-specific vulnerabilities, and demonstrates the security risks of improperly secured IoT devices. This project emphasizes the importance of securing IoT devices through practical demonstrations.

## 1. Objective

The primary objective of the **GenZai IoT Security Toolkit** project is to:

- **Scan Target URLs**: Identify IoT devices hosted on target URLs and detect potential security weaknesses.
- **Assess Vendor Vulnerabilities**: Use vendor-specific databases to check for default credentials and known vulnerabilities.
- **Demonstrate IoT Security Risks**: Showcase the importance of securing IoT devices via practical demonstrations of vulnerabilities.

## 2. Tools Used

### Programming Languages:
- **Golang** for backend functionality.
- **Python** and **Streamlit** for UI development.

### Libraries and Frameworks:
- **Go Backend**: `os`, `net/http`, `encoding/json`
- **Frontend**: `requests`, `pandas`, `streamlit`

### Databases:
- **signatures.json**: Contains IoT signature data for identifying devices.
- **vendor-logins.json**: Stores default vendor credentials for password scanning.
- **vendor-vulns.json**: Lists vendor-specific vulnerabilities.

### Tools and Platforms:
- **Postman**: For API testing and development.
- **VS Code**: For code development and debugging.
- **Docker**: For containerized deployment (optional).

## 3. Methodology

### Step 1: Setup Environment
1. Install Go and Python.
2. Install Streamlit and Python libraries from `requirements.txt`.
3. Set up the JSON databases in the project directory.

### Step 2: Initialize the Toolkit
- **Run the Backend**: Start the Go server with `go run main.go`.
- **Launch the Frontend**: Run the Streamlit UI with `streamlit run ui-main.py`.

### Step 3: Enter Target Information
- Users can either manually input target URLs or upload a file containing URLs.
- API endpoint configuration can be changed if required for specialized scanning.

### Step 4: Scan Targets
For each target URL, perform the following steps:
1. **Identify IoT devices** using signatures from `signatures.json`.
2. **Check for default vendor credentials** using `vendor-logins.json`.
3. **Scan for known vulnerabilities** using `vendor-vulns.json`.

### Step 5: Capture Results
- Log detailed results, including detected vulnerabilities and recommendations, into a specified output file (`results.log`).

## 4. Proof of Concept

### Example Scan Workflow:

1. Enter a target URL (e.g., `http://example-iot-device.com`).
2. The toolkit identifies the device type using signature matching.
3. It checks for default credentials (e.g., `admin:admin`) from `vendor-logins.json`.
4. It scans for known vulnerabilities and outputs the findings.
5. Results are displayed on the Streamlit UI and saved in a log file.

## 5. Conclusion

The **GenZai IoT Security Toolkit** emphasizes the critical need for robust security practices in IoT environments by demonstrating how insecure configurations can lead to vulnerabilities. Key takeaways include:

- The importance of securing IoT devices with strong credentials and firmware updates.
- Leveraging tools like GenZai to proactively identify and mitigate IoT vulnerabilities.
- The significance of securing IoT devices to safeguard against unauthorized access and data breaches.

---

**Note**: This project is intended for educational and research purposes. Always ensure proper consent when conducting security assessments on IoT devices.

## License

This project is licensed under the custom terms as stated in the [LICENSE](https://github.com/Nikith-S/GenZai-IoT-Security-Toolkit/blob/main/LICENSE) file of this repository. The software is provided "as is", for educational and research purposes only.

Please refer to the `LICENSE` file for the full terms and conditions.
