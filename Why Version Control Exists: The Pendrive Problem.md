# Why Version Control Exists: The Pendrive Problem

Before Git, GitHub, or any modern version control system existed, developers relied on something far less reliable: **pendrives, email attachments, and endless folders named “final”, “final\_v2”, “final\_latest\_really\_final”.**

If you’ve ever lost a file, overwritten your own work, or struggled to remember which version was the “real” one, you’ve already experienced the pain that led to the creation of version control.

Let’s walk through the story.

# **Why Version Control Exists**

Version control exists for one simple reason:

### **Humans are terrible at managing versions manually.**

We forget to save backups. We overwrite files. We lose track of what changed. We break things and have no way to go back.

Software development magnifies these problems:

* Multiple people work on the same files
    
* Changes happen constantly
    
* Mistakes can break entire projects
    
* Teams need a history of who changed what and why
    

Version control systems (VCS) like Git were created to solve these exact issues.

But to understand *why* they became essential, let’s revisit the dark ages of software development.

# **The Pendrive Analogy in Software Development**

Imagine a small team building a website in the early 2000s.

There’s no Git. No GitHub. No cloud storage. Just **pendrives** and **email attachments**.

### **A Typical Workflow Looked Like This:**

1. Developer A finishes some code
    
2. Copies it to a pendrive
    
3. Hands it to Developer B
    
4. Developer B makes changes
    
5. Saves it as `project_final.html`
    
6. Developer C edits it
    
7. Saves it as `project_final_latest.html`
    
8. Developer A overwrites it accidentally
    
9. Developer B loses the pendrive
    
10. Developer C emails a different version
    
11. No one knows which version is correct anymore
    

Chaos.

### **Diagram: Pendrive-Based Workflow**

Code

```powershell
Dev A → Pendrive → Dev B → Email → Dev C → Pendrive → Dev A
         ↑ Lost? Overwritten? Duplicate? No history.
```

This wasn’t just inconvenient & it was dangerous.

# **Problems Faced Before Version Control Systems**

Let’s break down the real issues teams faced.

## **1\. Overwriting Each Other’s Work**

Two developers editing the same file meant:

* One person’s changes overwrote the other’s
    
* No way to merge changes
    
* No way to see what was lost
    

### **Visual: Two Developers Editing the Same File**

```powershell
Dev A edits file.html
Dev B edits file.html
→ Only one version survives
```

## **2\. No History or Backup**

If something broke:

* There was no “undo”
    
* No previous version to restore
    
* No record of what changed
    

One mistake could destroy days of work.

## **3\. Duplicate Files Everywhere**

Teams created endless variations:

```powershell
index.html
index_final.html
index_final_v2.html
index_final_v2_latest.html
index_final_v2_latest_fixed.html
```

And no one knew which one was actually correct.

## **4\. Lost Pendrives, Lost Work**

A pendrive could:

* Get corrupted
    
* Be misplaced
    
* Contain outdated files
    
* Be overwritten accidentally
    

Your entire project could disappear with one bad day.

## **5\. No Collaboration Workflow**

There was no concept of:

* Branches
    
* Merging
    
* Pull requests
    
* Code reviews
    

Teams had to coordinate manually:

* “Don’t edit this file right now, I’m working on it”
    
* “Wait, which version are you using?”
    
* “Who changed this
