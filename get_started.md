⸻

✅ Step 1: Download Git for Windows
	1.	Open your browser
	2.	Go to https://git-scm.com
	3.	Click Download for Windows
	•	The download should start automatically

⸻

✅ Step 2: Install Git
	1.	Double-click the downloaded .exe file
	2.	Keep clicking Next with default settings
👉 The defaults are perfect for beginners
	3.	Important screen to notice:
	•	“Adjusting your PATH environment”
✔ Make sure “Git from the command line and also from 3rd-party software” is selected
	4.	Click Install
	5.	Click Finish

Done. Git is now installed 🎉

⸻

✅ Step 3: Open Git Bash (Your Git Terminal)

After install:
	•	Press Start
	•	Search for Git Bash
	•	Open it

You’ll see a black terminal window — this is where you’ll run Git commands.

⸻

✅ Step 4: Verify Git Works

In Git Bash, type:

git --version

If installed correctly, you’ll see something like:

git version 2.xx.x.windows.x

Boom 💥 Git is alive.

⸻

✅ Step 5: Set Your Name and Email (First-Time Setup)

Git needs to know who you are for commits.

git config --global user.name "Your Name"
git config --global user.email "your@email.com"

Example:

git config --global user.name "Ravi Kumar"
git config --global user.email "ravi@gmail.com"

Check it:

git config --list


⸻

✅ Step 6: Try Cloning a Repository

Now the fun part 😎

1️⃣ Go to a folder where you want your project

Example:

cd /c/Users/YourWindowsUsername/Desktop

2️⃣ Clone a repo

You can clone from GitHub like this:

git clone https://github.com/git/git.git

Git will download the project into a new folder.

⸻

✅ Step 7: Move Into the Project

cd git
ls

You are now inside a real Git repository 🎯

⸻

🧠 Most Basic Commands You’ll Use

Action	Command
Check Git version	git --version
Clone repo	git clone <url>
Go into folder	cd foldername
Check repo status	git status
See files	ls
