# What is git?
Git is is distributed version control system that store data in key - value. its means value is data and key is hash of data. we need key to retreive the content. The key are hashed with SHA-1 which produce 40-digit hexadecimal. Git will stored compressed data in BLOB with metadata in header:
 1. identifier BLOB
 2. size of content
 3. \0 as delimeter
 4. content

link : sample.stored-data-git.txt

# Stored Data Git
Git stores project information and its metadata into blob, tree, and commits objects. its data on .git folder on your repository.
directory structure are :
```
├── FETCH_HEAD
├── HEAD
├── branches
├── config
├── description
├── hooks
├── index
├── info
├── logs
├── objects
├── packed-refs
└── refs
```

BLOB will be store on **objects** folder.
git store information in a tree. 
A tree thet contains pointer: 
1. to blob
2. another tree

and metadata:
1. type of pointer (blob or tree)
2. filename or directory name
3. mode (executable file, symbolic link, etc)

Deleting .git folder will delete information and history of the project, but not the files of the project.

# Git Commits
git commit is an object that stores the current contents of the project in a new commit with a log message from the user describing the changes.
commits contains:
1. a tree

and metadata:
1. author and commiter
2. date
3. message
4. parent commit (one or more)

link : sample.commit-tree-git.txt
