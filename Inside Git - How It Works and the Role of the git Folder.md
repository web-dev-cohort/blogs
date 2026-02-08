# Inside Git: How It Works and the Role of the .git Folder

Most developers learn Git through commands—`git add`, `git commit`, `git push`—but few understand *what actually happens under the hood*. Git isn’t just a tool for saving code; it’s a sophisticated content‑addressable database that tracks your project with mathematical precision.

To truly master Git, you need to peek behind the curtain. This article walks you through Git’s internal architecture, the purpose of the `.git` folder, and how Git objects like blobs, trees, and commits work together to track changes.

## **How Git Works Internally**

Git is fundamentally a **distributed version control system** built around three core ideas:

### **1\. Snapshots, Not Diffs**

Unlike older systems (like SVN) that store differences between file versions, Git stores **snapshots** of your entire project at each commit. If a file hasn’t changed, Git simply references the previous version.

### **2\. Content‑Addressable Storage**

Every piece of data in Git is stored using a **SHA‑1 hash** of its contents. This means:

* If two files have identical content, Git stores them only once.
    
* Any corruption is immediately detectable because the hash won’t match.
    

### **3\. Immutable Objects**

Git stores data as immutable objects. Once created, an object never changes. New versions simply point to older ones, forming a chain of history.

This design makes Git:

* Fast
    
* Reliable
    
* Resistant to corruption
    
* Easy to distribute
    

## **Understanding the** `.git` **Folder**

When you run `git init`, Git creates a hidden directory called `.git`. This folder **is the entire repository**. Everything Git knows—history, branches, objects, configuration—lives inside it.

If you delete `.git`, your project becomes just a normal folder with no version history.

### **Key Components Inside** `.git`

| Folder/File | Purpose |
| --- | --- |
| `objects/` | Stores all Git objects (blobs, trees, commits) |
| `refs/` | Contains pointers to branches and tags |
| `HEAD` | Points to the currently checked‑out branch |
| `config` | Repository‑specific configuration |
| `index` | Staging area (used during `git add`) |
| `logs/` | Records movements of HEAD and branches |

### **Diagram: Structure of the** `.git` **Directory**

Code

```powershell
.git
 ├── objects/
 │    ├── ab/
 │    ├── cd/
 │    └── ...
 ├── refs/
 │    ├── heads/
 │    └── tags/
 ├── HEAD
 ├── index
 ├── config
 └── logs/
```

## **Git Objects: Blob, Tree, Commit**

Git stores everything as one of four object types. Understanding these is the key to understanding Git itself.

### **1\. Blob (Binary Large Object)**

A blob represents the **contents of a file**.

* No filename
    
* No metadata
    
* Just raw content
    

If two files have the same content, they share the same blob.

### **2\. Tree**

A tree represents a **directory**.

It contains:

* Filenames
    
* File modes (permissions)
    
* Pointers to blobs (files)
    
* Pointers to other trees (subdirectories)
    

### **3\. Commit**

A commit is a snapshot of your project at a point in time.

It contains:

* A pointer to a **tree** (root directory)
    
* Author and committer info
    
* Commit message
    
* Pointer(s) to parent commit(s)
    

### **4\. Tag (Annotated Tag)**

A tag is a human‑friendly label pointing to a commit.

### **Diagram: Relationship Between Commits, Trees, and Blobs**

Code

```powershell
Commit A
  |
  --> Tree (root)
        |
        ├── file1.txt --> Blob
        ├── file2.js  --> Blob
        └── src/      --> Tree
                           ├── index.js --> Blob
                           └── utils.js --> Blob
```

## **How Git Tracks Changes**

Git doesn’t track changes line‑by‑line. Instead, it tracks **snapshots** of your project and uses hashes to identify content.

Let’s break down what happens during `git add` and `git commit`.

## **What Happens During** `git add`

When you run:

Code

```powershell
git add file.txt
```

Git performs these steps:

1. **Reads the file content**
    
2. **Creates a blob object**
    
    * Compresses the content
        
    * Computes its SHA‑1 hash
        
    * Stores it in `.git/objects/`
        
3. **Updates the index (staging area)**
    
    * Records the filename
        
    * Records the blob’s hash
        
    * Prepares the file for the next commit
        

### **Internal Flow of** `git add`

Code

```powershell
Working Directory → Blob Object → Index (Staging Area)
```

## **What Happens During** `git commit`

When you run:

Code

```powershell
git commit -m "message"
```

Git performs:

### **1\. Creates a Tree Object**

Git reads the index and builds a tree structure representing your entire directory.

### **2\. Creates a Commit Object**

The commit object stores:

* Pointer to the tree
    
* Pointer to parent commit
    
* Author/committer info
    
* Commit message
    

### **3\. Updates Branch Reference**

If you're on `main`, Git updates:

Code

```powershell
.git/refs/heads/main
```

to point to the new commit hash.

### **4\. Updates HEAD**

HEAD continues pointing to the current branch.

### **Diagram: Internal Flow of** `git commit`

Code

```powershell
Index → Tree Object → Commit Object → Branch Pointer → HEAD
```

## **How Git Uses Hashes to Ensure Integrity**

Every Git object is stored using a SHA‑1 hash of its contents. This gives Git several superpowers:

### **1\. Integrity**

If any bit changes, the hash changes. Git instantly detects corruption.

### **2\. Deduplication**

Identical files produce identical hashes. Git stores them only once.

### **3\. Immutable History**

Because objects are hash‑linked, rewriting history requires rewriting all descendant commits.

This is why commands like `git rebase` rewrite commit hashes.

## **Building a Mental Model of Git**

Here’s the simplest way to think about Git:

* **Blob** = file content
    
* **Tree** = folder
    
* **Commit** = snapshot + message
    
* **Branch** = pointer to a commit
    
* **HEAD** = pointer to your current branch
    
* **Index** = staging area
    
* **.git folder** = the entire database
    

Git is basically a **key‑value store** where:

* Key = hash
    
* Value = object (blob/tree/commit)
    

Everything else—branches, tags, remotes—is just pointers.

## **Final Thoughts**

Once you understand Git’s internals, the commands start to make sense. You’re no longer memorizing syntax—you’re manipulating a database of snapshots.

The `.git` folder is the heart of your repository, and Git objects are the building blocks of your project’s history. With this mental model, you’ll find Git far more predictable, logical, and even elegant.

If you want, I can also generate:

* A shorter version for LinkedIn
    
* SEO‑optimized meta description
    
* A diagram‑only cheat sheet
    
* A visual explanation using ASCII art
