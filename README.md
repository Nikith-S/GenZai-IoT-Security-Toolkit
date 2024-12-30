GenZai: IoT Security Toolkit


A comprehensive toolkit for identifying and addressing vulnerabilities in IoT devices. GenZai enables you to scan target URLs, identify IoT devices, check for default credentials, and assess vulnerabilities using vendor-specific databases.

Developed with ❤️ by Nikith S.
Built With
Golang
Python
Streamlit
Getting Started
Prerequisites
Go: Ensure you have Go installed. Download here.
Python 3: Install Python. Download here.
Dependencies: Use go mod tidy for Go and pip install -r requirements.txt for Python.
Installation
Step 1. Clone the repository and navigate into the directory:

sh
Copy code
git clone https://github.com/Nikith-S/GenZai-IoT-Security-Toolkit.git
cd GenZai-IoT-Security-Toolkit
Step 2. Fetch Go dependencies:

sh
Copy code
go mod tidy
Step 3. Set up Python dependencies:

sh
Copy code
python -m venv venv
source venv/bin/activate  # For Linux/Mac
venv\\Scripts\\activate   # For Windows
pip install -r requirements.txt
Run the Toolkit
Step 4. Run the backend server:

sh
Copy code
go run main.go
Step 5. Launch the frontend:

sh
Copy code
streamlit run Genzai-UI/ui-main.py
Step 6. Open the frontend in your browser:

sh
Copy code
http://localhost:8501
Usage
The toolkit provides the following functionalities through its web UI:

Fingerprinting IoT Devices: Identifies IoT dashboards using signatures.json.
Default Password Check: Scans for vendor-specific default credentials using vendor-logins.json.
Vulnerability Assessment: Detects known vulnerabilities from vendor-vulns.json.
Example Workflow
Enter target URLs manually or upload a file containing target URLs.
Click Start Scan to begin analyzing the targets.
Review results in the UI or output logs for vulnerabilities, weak passwords, and security recommendations.
Stopping the Toolkit
To stop the backend or frontend processes:

Stop Backend:
Use Ctrl+C to terminate the Go server.

Stop Frontend:
Terminate the Streamlit process by closing the terminal or pressing Ctrl+C.

Contributors
Nikith S. (Primary Contributor): GitHub Profile
Manuals
Detailed manuals for using GenZai can be found in the docs directory.

