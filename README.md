# Repo: swe-bench_1 
## EECS 6444 Mining Software Engineering Data Assignment 1

##### Here’s a README file to guide you through the setup and execution of SWE-Agent within your project. This file outlines the environment setup, configuring Docker, linking SWE-Agent to GitHub, and running tasks.

---

*SWE-Agent Project Setup Guide:*

*This guide provides step-by-step instructions for setting up SWE-Agent within your project repository, using Anaconda for environment management and Docker for containerization.*



**Prerequisites 🚨**

•	Anaconda: Installed for environment management.
•	Docker: Installed for containerization. Download Docker from Docker’s website.
•	GitHub Account: Required for repository access, API token generation, and GitHub actions (optional).

---

#### *Project Setup 📋*

**Step 1: Clone This Project Repository**
	•	Clone the Repository:
	•		Open your terminal (or the integrated terminal in VS Code) and run: 
	
	git clone https://github.com/claudiafarkas/swe-bench_1.git 
	cd swe-bench_1



**Step 2: Download SWE-Agent and Create a Conda Environment**
	*1.	Clone SWE-Agent:*
	•	In your project directory, clone SWE-Agent:

	git clone https://github.com/princeton-nlp/SWE-agent.git

*2.	Create a Conda Environment:*
	•Open Anaconda Navigator and go to the Environments tab.
	•Click Create, name the environment (e.g., swe-agent), and select: `Python 3.8 or higher`

*3.	Install Dependencies:*
	•	In the terminal within Anaconda Navigator or VS Code, activate the environment and install dependencies:
	
	conda activate swe-agent
	conda env update -f SWE-agent/environment.yml



**Step 3: Configure Docker**

1.	Install Docker:
•Download Docker from Docker’s website and install it following the on-screen instructions for your operating system.
2.	Start Docker:
•	Ensure Docker is running on your machine. Open Docker Desktop and verify it is active.
3.	Verify Docker Installation:
•	Run this command in your terminal to confirm Docker is set up correctly: `docker --version`



**Step 4: Set Up API Keys for SWE-Agent**

1.	Generate a GitHub Token:
•	Go to GitHub’s Personal Access Tokens page and click Generate new token.
•	Select permissions, such as repo for repository access, and copy the token.
2.	Create a keys.cfg File:
•	Inside the SWE-agent directory, create a file called keys.cfg and add your tokens:

```
GITHUB_TOKEN=your_github_token
OPENAI_API_KEY=your_openai_key (optional)
ANTHROPIC_API_KEY=your_anthropic_key (optional)
```


**Step 5: Run the Setup Script**

1.	Execute the Setup Script:
•	In your terminal, navigate to the SWE-Agent directory and run: `./setup.sh`
•	This script will configure the Docker container for SWE-Agent.

---

*Running SWE-Agent on GitHub Issues*

1.	Navigate to Your Project Directory:
•	Open a terminal in the root directory of your project repository.
2.	Run SWE-Agent:
•	Use SWE-Agent on a GitHub issue by specifying the issue URL:`python SWE-agent/run.py --input https://github.com/your-username/swe-bench_1/issues/1`

3.	Review and Commit Changes:
•	Review the changes made by SWE-Agent, then commit and push them:
```
git add .
git commit -m "Apply SWE-Agent's changes for Issue #1"
git push origin main
```

---
*Additional Notes 📝*

•	Logs: Check the logs/ directory in the SWE-Agent folder for detailed outputs from each run.
•	Environment Management: To manage your Conda environment within Anaconda Navigator, simply activate or deactivate it as needed.
•	Automate with GitHub Actions (Optional): You can set up GitHub Actions workflows to automate SWE-Agent tasks on new issues. Store your GitHub token securely in the GitHub Actions environment.


 **This completes the setup for running SWE-Agent within your project repository. If you encounter any issues, consult Docker and Conda documentation, or refer to the SWE-Agent GitHub repository for further guidance.**
