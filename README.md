# Learn Python backend, with Claude Code as your tutor

A course that takes you from zero to junior Python backend developer. Each lesson is 60–75 minutes: theory, a few check questions, a task you code yourself, a review, and your takeaways. Claude teaches and reviews. **You write all the code.**

## One-time setup (Windows)

1. **Git for Windows**: install from git-scm.com with the default options. It includes *Git Bash*, the terminal you'll use.
2. **Python 3.12 or newer**: install from python.org and tick **"Add python.exe to PATH"** on the first screen.
   Open Git Bash and run `python --version`. If the Microsoft Store opens instead, go to *Settings → Apps → Advanced app settings → App execution aliases* and turn off `python.exe` and `python3.exe`.
3. **VS Code**: install it, then press `Ctrl+Shift+P`, choose *Terminal: Select Default Profile*, and pick **Git Bash**.
4. **Claude Code**: install it with the official Windows instructions, then run `claude` once to log in.
5. **Get the course** (the maintainer adds you to your own GitHub repo first and sends you its link):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   git clone <your repo link>
   cd <repo folder>
   claude
   ```
   When Claude asks whether to trust the folder, say yes.

## Every lesson

| Type | When |
|---|---|
| `/next` | Start a lesson, or pick up where you left off |
| `/review` | Your code is ready to be checked |
| `/done` | After approval: write your takeaways and finish |
| `/park` | Need to stop in the middle; your code is saved |
| `/status` | See your progress |

Take the 15-minute break between lessons. Three lessons a day is the plan, but you set the pace.

To run your code: `python main.py` inside the lesson's `work/` folder. To run the tests: `python tools/learn.py test` from the course folder.

## For the maintainer

- **One repo per learner**: each learner gets their own repo and works on its `main`, so nobody can touch anyone else's progress. The `course` branch of `job_enabler_666` holds the course with no learner progress. Make course changes there, then in each learner's clone run `git pull course course && git push`.
- **Add a learner**: create an empty private repo, then `git clone --branch course --single-branch <job_enabler_666 path> <folder>`, and in it `git branch -m course main`, `git remote rename origin course`, `git remote add origin <new repo>`, `git push -u origin main`. Add them as a collaborator on the new repo only.

- **Plan a week**: `/plan-week`, optionally with notes like `/plan-week go slower on dicts`. It plans 15 lessons, builds and checks each one, then commits and pushes.
- **Check progress**: `/status`, `python tools/learn.py status`, or `git log`. Every lesson step is its own commit.
- **Change the course**: `roadmap/roadmap.json` is the curriculum. Never rename concept ids, because lessons and mastery scores refer to them.
- How it all fits together is in [DESIGN.md](DESIGN.md).
