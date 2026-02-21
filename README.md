<p align="center">
  <img src="./img.png" alt="Project Banner" width="100%">
</p>

# Pulse Chain 🎯

## Basic Details

### Team Name: Hack Wave

### Team Members
- Member 1: Parvathy Abhilash - College of engineering munnar
- Member 2: Anwaya V - College of engineering munnar

### Hosted Project Link
[https://drive.google.com/file/d/1YEFUNmNUwWJK4LEduc_k8CE1Pt_NaJVG/view?usp=drivesdk](https://drive.google.com/file/d/1YEFUNmNUwWJK4LEduc_k8CE1Pt_NaJVG/view?usp=drivesdk)

### Project Description
PulseChain is a full-stack blood donation platform that connects donors and seekers in real time. Donors can toggle availability and earn reward points, while seekers send emergency blood requests to nearby donors. Built with React, Node.js, and MongoDB, it enables fast alerts, live leaderboard tracking, and scalable life-saving coordination.

### The Problem statement
In medical emergencies, finding compatible blood donors quickly is still slow, manual, and unreliable. Hospitals and families often depend on phone calls, social media posts, or blood banks that may not have real-time availability. There is no unified system that connects nearby, available donors instantly to patients in need. This delay can cost critical time — and lives.

### The Solution
PulseChain provides a real-time digital platform that directly connects blood donors and seekers. Donors can register, update their availability, and earn reward points for participation. Seekers can instantly send emergency blood requests, which are routed to nearby compatible donors. The system uses a centralized backend with live updates, enabling faster response, better coordination, and efficient life-saving support.

---

## Technical Details

### Technologies/Components Used

**For Software:**
- Languages used: [HTML,css,javascript,PostgreSQL]
- Frameworks used:  React

- Tools used: [e.g., VS Code, Git,render]



---

## Features

List the key features of your project:
- Feature 1:Real-Time Emergency Alerts – Seekers can send instant blood requests that notify nearby compatible donors immediately.
- Feature 2:Donor Availability Toggle – Donors can update their availability status in real time, ensuring only active donors receive alerts.
- Feature 3: Smart Leaderboard & Reward System – Donors earn points for participation, encouraging regular engagement through gamification.
- Feature 4: Full-Stack Scalable Architecture – Built with React, Node.js, and MongoDB, enabling secure data storage, API-based communication, and future scalability.

---

## Implementation

### For Software:

#### Installation
```bash
[Installation commands -npm install, npm install express cors dotenv]
```

#### Run
```bash
[Run commands - npm start]
```


---

## Project Documentation

### For Software:

#### Screenshots (Add at least 3)

![Screenshot1][(Add screenshot 1 here with proper name)](https://drive.google.com/file/d/11EJScf2LLI5PyatuQYTCX_KsOTF_FwmO/view?usp=drivesdk)
PulseChain Home Page showcasing the main landing interface with navigation menu, welcome message, and quick action buttons for donors and seekers to access the platform instantly.

![Screenshot2][(Add screenshot 2 here with proper name)](https://drive.google.com/file/d/1RLD8KEsC_ZOi4aUVn3eqjPocgEDddCib/view?usp=drivesdk)
User Registration Interface where donors or seekers can create an account by entering personal details, selecting blood group, and choosing their role within the platform.

![Screenshot3][(Add screenshot 3 here with proper name)](https://drive.google.com/file/d/1V3R_0EuaUTETi0NIB2ey5wl52vK-cRe_/view?usp=drivesdk)
Donor Dashboard displaying nearby active donors, search and filter options by blood group, and quick contact functionality to enable fast emergency response coordination.

#### Diagrams

**System Architecture:**

![Architecture Diagram][(docs/architecture.png)](https://drive.google.com/file/d/1Ce89uod5nPqOomFpN3BrQ9hga4xCINVc/view?usp=drivesdk)
PulseChain follows a full-stack client–server architecture where the React frontend handles user interaction and communicates with a Node.js and Express backend through REST APIs. The backend manages authentication, donor availability, emergency requests, and reward calculations, while applying location-based filtering (5 km logic). All data, including users, requests, and points, is stored securely in MongoDB. This modular architecture ensures scalability, real-time coordination, and efficient life-saving response during emergencies.

**Application Workflow:**

![Workflow](docs/workflow.png)
The workflow begins with user authentication, where donors or seekers register and log in through the React frontend. Donors can update their availability status, while seekers submit emergency blood requests. The backend processes requests, applies blood group matching and 5 km location filtering, retrieves eligible donors from MongoDB, and returns results to the frontend. Upon successful donation, reward points are updated and reflected in the leaderboard system.

---

### For Hardware:

#### Schematic & Circuit

![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

#### Build Photos

![Team](Add photo of your team here)

![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

---

## Additional Documentation

### For Web Projects with Backend:

#### API Documentation

**Base URL:** `[https://api.yourproject.co](https://drive.google.com/file/d/1YEFUNmNUwWJK4LEduc_k8CE1Pt_NaJVG/view?usp=drivesdk)m`

##### Endpoints

**GET /api/endpoint**
- **Description:** [What it does]
- **Parameters:**
  - `param1` (string): [Description]
  - `param2` (integer): [Description]
- **Response:**
```json
{
  "status": "success",
  "data": {}
}
```

**POST /api/endpoint**
- **Description:** [What it does]
- **Request Body:**
```json
{
  "field1": "value1",
  "field2": "value2"
}
```
- **Response:**
```json
{
  "status": "success",
  "message": "Operation completed"
}
```

[Add more endpoints as needed...]

---

### For Mobile Apps:

#### App Flow Diagram

![App Flow](docs/app-flow.png)
*Explain the user flow through your application*

#### Installation Guide

**For Android (APK):**
1. Download the APK from [Release Link]
2. Enable "Install from Unknown Sources" in your device settings:
   - Go to Settings > Security
   - Enable "Unknown Sources"
3. Open the downloaded APK file
4. Follow the installation prompts
5. Open the app and enjoy!

**For iOS (IPA) - TestFlight:**
1. Download TestFlight from the App Store
2. Open this TestFlight link: [Your TestFlight Link]
3. Click "Install" or "Accept"
4. Wait for the app to install
5. Open the app from your home screen

**Building from Source:**
```bash
# For Android
flutter build apk
# or
./gradlew assembleDebug

# For iOS
flutter build ios
# or
xcodebuild -workspace App.xcworkspace -scheme App -configuration Debug
```

---

### For Hardware Projects:

#### Bill of Materials (BOM)

| Component | Quantity | Specifications | Price | Link/Source |
|-----------|----------|----------------|-------|-------------|
| Arduino Uno | 1 | ATmega328P, 16MHz | ₹450 | [Link] |
| LED | 5 | Red, 5mm, 20mA | ₹5 each | [Link] |
| Resistor | 5 | 220Ω, 1/4W | ₹1 each | [Link] |
| Breadboard | 1 | 830 points | ₹100 | [Link] |
| Jumper Wires | 20 | Male-to-Male | ₹50 | [Link] |
| [Add more...] | | | | |

**Total Estimated Cost:** ₹[Amount]

#### Assembly Instructions

**Step 1: Prepare Components**
1. Gather all components listed in the BOM
2. Check component specifications
3. Prepare your workspace
![Step 1](images/assembly-step1.jpg)
*Caption: All components laid out*

**Step 2: Build the Power Supply**
1. Connect the power rails on the breadboard
2. Connect Arduino 5V to breadboard positive rail
3. Connect Arduino GND to breadboard negative rail
![Step 2](images/assembly-step2.jpg)
*Caption: Power connections completed*

**Step 3: Add Components**
1. Place LEDs on breadboard
2. Connect resistors in series with LEDs
3. Connect LED cathodes to GND
4. Connect LED anodes to Arduino digital pins (2-6)
![Step 3](images/assembly-step3.jpg)
*Caption: LED circuit assembled*

**Step 4: [Continue for all steps...]**

**Final Assembly:**
![Final Build](images/final-build.jpg)
*Caption: Completed project ready for testing*

---

### For Scripts/CLI Tools:

#### Command Reference

**Basic Usage:**
```bash
python script.py [options] [arguments]
```

**Available Commands:**
- `command1 [args]` - Description of what command1 does
- `command2 [args]` - Description of what command2 does
- `command3 [args]` - Description of what command3 does

**Options:**
- `-h, --help` - Show help message and exit
- `-v, --verbose` - Enable verbose output
- `-o, --output FILE` - Specify output file path
- `-c, --config FILE` - Specify configuration file
- `--version` - Show version information

**Examples:**

```bash
# Example 1: Basic usage
python script.py input.txt

# Example 2: With verbose output
python script.py -v input.txt

# Example 3: Specify output file
python script.py -o output.txt input.txt

# Example 4: Using configuration
python script.py -c config.json --verbose input.txt
```

#### Demo Output

**Example 1: Basic Processing**

**Input:**
```
This is a sample input file
with multiple lines of text
for demonstration purposes
```

**Command:**
```bash
python script.py sample.txt
```

**Output:**
```
Processing: sample.txt
Lines processed: 3
Characters counted: 86
Status: Success
Output saved to: output.txt
```

**Example 2: Advanced Usage**

**Input:**
```json
{
  "name": "test",
  "value": 123
}
```

**Command:**
```bash
python script.py -v --format json data.json
```

**Output:**
```
[VERBOSE] Loading configuration...
[VERBOSE] Parsing JSON input...
[VERBOSE] Processing data...
{
  "status": "success",
  "processed": true,
  "result": {
    "name": "test",
    "value": 123,
    "timestamp": "2024-02-07T10:30:00"
  }
}
[VERBOSE] Operation completed in 0.23s
```

---

## Project Demo

### Video
[[Add your demo video link here - YouTube, Google Drive, etc.]](https://drive.google.com/file/d/1YEFUNmNUwWJK4LEduc_k8CE1Pt_NaJVG/view?usp=drivesdk)

The video demonstrates the complete PulseChain user journey, starting with user authentication and role selection (donor or seeker). It showcases the donor dashboard where users can toggle availability and view the leaderboard, followed by the seeker interface used to send emergency blood requests. The demo highlights real-time request handling, donor matching logic, and dynamic leaderboard updates. Technically, it illustrates the interaction between the React frontend, Node.js/Express backend APIs, and MongoDB database, emphasizing full-stack integration, REST API communication, and scalable system design.

### Additional Demos
[Add any extra demo materials/links - Live site, APK download, online demo, etc.]

---

## AI Tools Used (Optional - For Transparency Bonus)

If you used AI tools during development, document them here for transparency:chatgpt, github copilot

**Tool Used:** [e.g., GitHub Copilot, v0.dev, Cursor, ChatGPT, Claude]

**Purpose:** [What you used it for]
- Example: "Generated boilerplate React components"
- Example: "Debugging assistance for async functions"
- Example: "Code review and optimization suggestions"

**Key Prompts Used:**
- "Create a REST API endpoint for user authentication"
- "Debug this async function that's causing race conditions"
- "Optimize this database query for better performance"

**Percentage of AI-generated code:** [Approximately X%]

**Human Contributions:**
- Architecture design and planning
- Custom business logic implementation
- Integration and testing
- UI/UX design decisions

*Note: Proper documentation of AI usage demonstrates transparency and earns bonus points in evaluation!*

---

## Team Contributions

- [Anwaya V]: [Specific contributions - e.g., Frontend development.]
- [Parvathy Abhilash]:  e.g., Backend development]
- 

---

## License

This project is licensed under the [LICENSE_NAME] License - see the [LICENSE](LICENSE) file for details.

**Common License Options:**
- MIT License (Permissive, widely used)
- Apache 2.0 (Permissive with patent grant)
- GPL v3 (Copyleft, requires derivative works to be open source)

---

Made with ❤️ at TinkerHub
