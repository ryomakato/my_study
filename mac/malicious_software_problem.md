# App problem
 “Visual Studio Code” can’t be opened because Apple cannot check it for malicious software.

# How to solve this problem

- 1. Move the app to the Applications folder
- 2. Open Terminal.app, then paste and execute the following command:
```bash:
$ xattr -d com.apple.quarantine /Applications/Visual\ Studio\ Code.app
```

### References
- https://stackoverflow.com/questions/58457958/visual-studio-code-cant-be-opened-because-apple-cannot-check-it-for-malicious
