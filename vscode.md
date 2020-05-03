# Using Visual Studio Code with Git

VSCode docs are [here](https://code.visualstudio.com/docs/editor/versioncontrol) for working with version control, including Git.

You will need to install Git and also Git Credential Manager for Windows, to stop you getting errors of "Host key verification failed"

Alternatively you could try [Visual Studio Codespaces](https://visualstudio.microsoft.com/services/visual-studio-online/) which was formerly known as Visual Studio Online. Please note that it isn't working straight off if you use git protocol to clone, so suggest using https.

## Variables for Git

You'll probably want to set some like below:

```
git config --global core.editor "vim"
git config --global core.autocrlf false  
git config --global user.name "Your Name"
git config --global user.email "you@yourdomain.com"
```

The _global_ means system wide, you can omit it to alter for a project. 

The _core.autocrlf_ setting could ignite a whole debate, as many people on Windows suggest using _true_ as a parameter. As a very short primer - Windows defaults to CRLF at the end of a line where Mac/Linux defaults to LF. I prefer false so that files don't get altered, and check in the bottom right of VSCode windows that LF is showing for the file. If it isn't you can change the type by clicking on the CRLF text.

To see the current environment variables type `git config --list`