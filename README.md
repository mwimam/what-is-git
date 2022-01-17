# What is git?
Git is is distributed version control system that store data in key - value. its means value is data and key is hash of data. we need key to retreive the content. The key are hashed with SHA-1 which produce 40-digit hexadecimal. Git will stored compressed data in BLOB with metadata in header:
 1. identifier BLOB
 2. size of content
 3. \0 as delimeter
 4. content

link : sample.stored-data-git.txt

# Stored Data Git
Git stores its data on .git folder on your repository. directory structure are :
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

BLOB will be store on objects folder