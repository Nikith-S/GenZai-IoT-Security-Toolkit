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
<h1 align="center">GenZai</h1> <p align="center"><b>The IoT Security Toolkit</b></p> <p align="center"> <a href="#description">Description</a> • <a href="#features">Features</a> • <a href="#setup">Setup & Usage</a> • <a href="#acknowledgements">Acknowledgements</a> • <a href="#contact">Contact Me</a><br> <p align="center"> <img src="https://img.shields.io/badge/Version-2.0-green"> <img src="https://img.shields.io/badge/Black%20Hat%20Arsenal-%20Asia%202024-blue"> <img src="https://img.shields.io/badge/Black%20Hat%20Arsenal-%20MEA%202024-blue"> <img src="https://img.shields.io/badge/GISEC%20Armory-%20Dubai%202024-blue"> <a href="https://www.buymeacoffee.com/NikithS" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 21px !important;width: 94px !important;" ></a> </p> <hr> <img src="./genzai.png"> <hr style="width:300px; height: 1px; margin: auto; margin-top: 20px;" /> <br> <div id="description"> <h2> Description </h2> Genzai helps you identify IoT or Internet of Things-related dashboards across a single or set of targets provided as input and scan them for default password issues and potential vulnerabilities based on paths and versions.
An example would be an admin panel for a home automation device accessible over the internet. The tool will first fingerprint the IoT (product) based on a set of signatures from <a href="./signatures.json">signatures.json</a> and then, based on the product identified and the relevant templates in its DBs (<a href="./vendor-logins.json">vendor-logins.json</a> and <a href="./vendor-vulns.json">vendor-vulns.json</a>), scan it for vendor-specific default passwords like admin:admin and look for any potential vulnerabilities.
Genzai currently supports fingerprinting over 20 IoT-based dashboards and has the same amount of templates to look for default password issues across them. It currently has a total of 10 vulnerability templates, which will increase with coming updates.
</div> <hr style="height: 1px;"> <div id="features"> <h2> Features </h2> <h4>Fingerprinting - The Wappalyzer of IoT Devices</h4> With Genzai, you can fingerprint the IoT Product running over a target based on the HTTP response received through it. With support for 20 templates and counting, Genzai can look for categories such as:
Wireless Router
Surveillance Camera
HMI or Human Machine Interface
Smart Power Control
Building Access Control System
Climate Control
Industrial Automation
Home Automation
Water Treatment System
<h4>Default Password Checks</h4> Using the <a href="./vendor-logins.json">Vendor Logins DB</a>, Genzai will check if the target is still using vendor-specific default passwords. <h4>Vulnerability Scanning</h4> Using the <a href="./vendor-vulns.json">Vendor Vulns DB</a>, Genzai scans for any potential vulnerabilities across the target. </div> <div id="setup"> <h2> Setup & Usage </h2> <h4> Clone the Repository </h4> ```bash git clone https://github.com/Nikith-S/GenZai-IoT-Security-Toolkit.git cd GenZai-IoT-Security-Toolkit ``` <h4> Backend Setup </h4> ```bash # Fetch Go dependencies go mod tidy
<h4> Frontend Setup </h4>
```bash
# Set up a Python virtual environment
python -m venv venv
source venv/bin/activate  # For Linux/Mac
venv\\Scripts\\activate   # For Windows
# Install dependencies
pip install -r requirements.txt
# Launch the Streamlit UI
streamlit run Genzai-UI/ui-main.py
<h4> Perform a Scan </h4> - Enter target URLs manually or upload a file containing URLs in the UI. - Change API endpoint if required. - Click **Start Scan** and review the results in the UI or output logs. </div> <div id="acknowledgements"> <h2> Acknowledgements </h2> GenZai has been or will be noticed at: <ul type="disc"> <li><a href="https://www.blackhat.com/asia-24/arsenal/schedule/index.html#genzai---the-iot-security-toolkit-37373">Black Hat Asia 2024 [Arsenal]</a></li> <li><a href="https://www.gisec.ae/gisec-armory">GISEC Armory Edition 1 Dubai 2024</a></li> <li><a href="https://blackhatmea.com/agenda-2024">Black Hat MEA 2024 [Arsenal]</a></li> </ul> </div> <div id="contact"> <h2> Let's Connect! </h2> If you have any questions or feedback about Genzai or just want to connect, feel free to reach out via: - [LinkedIn](https://in.linkedin.com/in/umair-nehri-49699317a) - [Email](mailto:umairnehri9747@gmail.com) </div> <h2>Legal Disclaimer</h2> Usage of Genzai for scanning or attacking targets without prior mutual consent is illegal. It is the end user's responsibility to obey all applicable local, state, and federal laws. Developers assume no liability and are not responsible for any misuse or damage caused by this program.
