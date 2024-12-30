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
