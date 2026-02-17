# Privacy Policy for saMacros

**Last Updated: February 17, 2026**

### 1. No Data Collection by Core Application
We believe in absolute privacy. **The saMacros core application does not collect, harvest, transmit, or store any personal identifiable information (PII).** There are no hidden analytics, tracking scripts, or telemetry embedded in the software.

### 2. Local Operation & Data Sovereignty
By default, the application operates entirely on your local machine.
* **Macro & Script Files:** Your recorded sequences (.mmc) and scripts (.js) are stored locally. These files remain under your total control.
* **Core Security:** The core application does not initiate any network connections unless explicitly triggered by a user-defined script or plugin.

### 3. Third-Party Scripts and Plugins (Important)
saMacros features a powerful scripting engine (GraalJS) that allows the execution of third-party scripts.
* **User Responsibility:** When you download and run a script or plugin from a third party, that script may have the technical capability to access the internet or local files.
* **Security Mechanism:** We provide a `white_list.json` to help you manage trusted sources. However, **saMacros is not responsible for the privacy practices or actions of third-party scripts.** Always review the source code of a script before execution.

### 4. Local Configuration and Storage
To provide a consistent experience, the app stores configuration files in your system's `AppData` directory (`%USERPROFILE%/AppData/saMacros/`):
* **config.cfg**: Stores UI settings, language, and hotkey mappings.
* **cache.json**: Stores window dimensions and recent file paths.
* **white_list.json**: Stores your manually approved trusted script authors and script signatures.
  These files never leave your computer and can be deleted at any time.

### 5. System Permissions Usage
To function as an automation tool, saMacros requires the following local system access:
* **Input Monitoring & Injection**: The app monitors and simulates mouse/keyboard events for automation. This data is processed in real-time and is never stored unless you are actively "Recording."
* **Scripting Engine Access**: The GraalJS engine requires permission to execute logic on your CPU. Depending on the script's content, it may request broader system access.

### 6. Third-Party Links
Our documentation or GitHub page may contain links to other sites. We have no control over and assume no responsibility for the content or privacy policies of any third-party sites or services.

### 7. Contact Us
If you have any questions about this Privacy Policy or script security, please reach out via:
* **GitHub Issues**: [Samera2022/saMacros/issues](https://github.com/Samera2022/saMacros/issues)