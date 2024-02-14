# Git Security
There are a number of ways in which a git repository can be compromised (this isn't a security flaw, just a fact of life—one should not avoid using git because of this). For example, someone may have pushed to your repository claiming to be you. Or for that matter, someone could have pushed to someone else's repository claiming to be you (someone could push to their own repository claiming to be you too). This is just part of life in a DVCS.

Just as an example:
```
$ git config --global user.name 'Madara Uchiha'
$ git config --global user.email muchiha@example.com
```
---
## Best Practices
- Restrict and Control Access: Enforce strict access controls to prevent unauthorized access to your repositories
- Protect Your Code Branches
-  Keep Secrets Away from Code
- Scan for Vulnerabilities
- Beware of Forks

new line