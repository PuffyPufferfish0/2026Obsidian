### Git (Version Control)

A system that records changes to a file or set of files over time so that you can recall specific versions later.

### The Three States

1. **Working Directory**: The files you are currently modifying.
    
2. **Staging Area**: Files marked to be committed (`git add`).
    
3. **Repository**: Where the committed history is permanently stored (`git commit`).
    

### Essential Workflow Commands

- `git clone [URL]` : Download a remote repository to your local machine.
    
- `git status` : Check what files are modified or staged.
    
- `git add [file]` : Add a new or modified file to the staging area.
    
- `git commit -m "message"` : Save staged changes locally with a descriptive message.
    
- `git push` : Upload local commits to the remote repository (e.g., GitHub).
    
- `git pull` : Download changes from the remote repository and merge them into your local branch.

# EXAM II extra info
# Git (Version Control)

Git is a version control system used to track changes in code over time and collaborate with others.

### Key Concepts

- **Repository (Repo)**: The directory where your tracked files live.
    
- **Commit**: A snapshot of your files at a specific point in time.
    

### Basic Workflow Commands

1. `git clone <ssh-url>` : Downloads a repository to your local machine (using SSH authentication).
    
2. `git status` : Shows the current state of your working directory (what's modified, what's staged).
    
3. `git add <file>` : Stages a file, preparing it to be committed.
    
4. `git commit -m "Message"` : Saves the staged changes to local history with a descriptive message.
    
5. `git push` : Uploads your local commits to the remote repository (e.g., GitHub or GitLab).
    
6. `git pull` : Downloads remote commits and merges them into your local workspace.