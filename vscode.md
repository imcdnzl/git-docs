# Using Visual Studio Code with Git

## Installing for Windows
You will need to install Git and also [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows) - the latter to stop you getting errors of "Host key verification failed"

The default options are mostly OK, but I'd change the default editor to VSCode, and also the line editing coversions to "checkout as-is, commit as-is".

## Using an online workspace
Alternatively you could try [Visual Studio Codespaces](https://visualstudio.microsoft.com/services/visual-studio-online/) which was formerly known as Visual Studio Online. The documentation can be found [here](https://docs.microsoft.com/en-us/visualstudio/online/overview/what-is-vsonline). Please note that it isn't working straight off if you use git protocol to clone, so suggest using https (see [here](https://docs.microsoft.com/en-us/visualstudio/online/reference/repository) for more details).

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

The `core.editor` setting is only if you're going to use VSCode on a box without a GUI.

To see the current environment variables type `git config --list`

## Misc
If you get prompted to turn on auto fetch it's pretty safe to do so - it grabs commits others have made, or you might have made elsewhere. NB It doesn't merge them or overwrite - you still need to do some form of git pull.

If you are doing any commits from GitHub website and want to change email addresses have a read of [this](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address)

VSCode docs are [here](https://code.visualstudio.com/docs/editor/versioncontrol) for working with version control, including Git.