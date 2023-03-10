# Installing Software for CompSci 201

You will need Java, VS Code, and Git to complete work in Compsci 201. Installation of these is described below. While all related software is compatible with Linux, these instructions have only been tested on Mac and Windows machines.

## Installing Java and VS Code

Java is the programming language we use in the course. You will need to install a Java Development Kit (JDK) in order to get access to a Java Virtual Machine (which runs your code) and the base packages / standard library in Java. We will use Open JDK 17 (the most recent JDK with long-term support) for the course. 

Visual Studio Code (VS Code) is a modern and extensible text editor. You will use this to read, write, and (with extensions) run and debug your code.

For those with Mac or Windows machines, installation of Java and VS Code along with the necessary extensions is a one step process. **Go to the [Getting Started with Java in VS Code page](https://code.visualstudio.com/docs/java/java-tutorial) and select to install the coding pack for your machine/operating system. You should not need to change any defaults during installation. If you have a Linux machine, you will need to read the rest of the guide and separately install Open JDK 17 (sources are provided in the article), VS Code, and the Java Extension Pack for VS Code.

### Launching JShell

JShell is an interactive tool that allows you to write and execute Java statements on the command line. You can declare variables, execute Java statements and view the values of variables in real time, without having to create a class or a main method.

***You do not necessarily need to use JShell for the purpose of CompSci 201, but you’re recommended to***. JShell is very helpful if you have conceptual questions about Java and want to verify them using simple examples: for instance, if you’re not sure how the `HashSet.retainAll()` method behaves, you can open JShell, create two `HashSet` objects with some values, make a call to `retainAll()` and observe the new values of the two sets.

While you don’t need to know how to use JShell right now, ***we recommend running it at least once to verify it is working as intended***. Once you have Java installed, you should be able to use JShell immediately:

1. Open a Terminal on Mac or Command Prompt on Windows.

2. Type `jshell` and press Enter.
If the Java installation worked properly, you should see a welcoming message, and then you should be able to type Java expressions:

If you receive a response such as `"jshell": command not found`, it is likely that you did not download the most recent version of the JDK (Version 17 as of January 2022). To confirm what version you downloaded, run the command `java -version` in your command line. If that command returns a versioning error, you will need to update the operating system on your device before proceeding. 

If you still encounter difficulties after following the above steps, it probably means the Java installation path was not added to the system’s PATH variable. Follow [this guide](https://community.akamai.com/customers/s/article/Adding-JDK-Path-in-Mac-OS-X-Linux-or-Windows?language=en_US) to add it to PATH. If you are a Mac user, the path command you should append to the end of the file by running `vi ~/.bash_profile` be something like `export PATH=$PATH:/Library/Java/JavaVirtualMachines/liberica-jdk-17.jdk/Contents/Home/bin/`. 

For more tips running vim, refer to [this page](https://www.radford.edu/~mhtay/CPSC120/VIM_Editor_Commands.htm). In summary, press the right key until your cursor is at the end of the file, then type in `:i` and enter. You should now be in INSERT mode and be able to type in the above command. After you're done editing, press `:wq` in order to exit Vim.

The Windows path would be similar to `C:/Program Files/BellSoft/LibericaJDK-17/bin/` and you would go to "Edit environment variables" on your Windows computer.

In either case, please check that this path exists on your device before proceeding with adding it.

<div align="middle">
  <img src="images/jshell_mac.png" width="400" />
</div>

***While JShell allows you to use basic Java functionality and expressions, it is not what we use for coursework in CompSci 201. Most of the coding will be done in VS Code, as described below.***

You can type `/exit` to quit jshell in your terminal.

### Launch and Configure Visual Studio Code
After installation, you should be able to run Visual Studio Code and if so, you'll be greeted with a screen like the following. If you wish, you can further customize the screen (like the author has!) by going to File -> Preferences -> Settings.

<div align="middle">
  <img src="images/vscode-splash.png" width="400" />
</div>

In CompSci 201, you will mainly use “Open Folder” for assignments (large-scale Java projects) and create your own folder for APTs. Once you have worked on some projects with VS Code, a list of recently opened projects can be found under "Open Recent."

### (Optional) Change Program Output from Console to Terminal

VS Code will run your Java files, but the default setting for program output will spit out a long command used to run your code - to get rid of this command (and just get your program's output), try these steps.

- Code/File 
- -> Preferences 
- -> Settings 
- -> search "java debug settings" 
- -> Change "Debug - Settings: Console" prompt from "integratedTerminal" -> "internalConsole"

<div align="middle">
  <img src="images/internalConsole.png" width="500" />
</div>

### Organizing Your Code

Unlike some other IDEs, VS Code works with folders, not "VS Code projects." Any folder/directory that exists on your computer can be opened in VS Code with `File > Open`. For this course, you’ll work with folders that each store a collection of related Java files that you will code, run, and test.

For CS 201, you should set up a folder to store your code related to this course. It should be
1. in a location that you will remember
2. in a format/structure that makes sense to you

We recommend the following folder setup:

```
▼ CS 201
  ▼ APT
    ▼ APT 1
      - AccessLevel.java
      - CirclesCountry.java
    ▼ APT 2
      - TxMsg.java
      - ...
  ▼ Projects
    ▶ P0-Person201
    ▶ P1-NBody
    - ...
```
You do not have to create the individual subfolders under APTs or Projects yet - instead, you can create them throughout the course, as necessary.

### Testing VS Code + Java

While you don’t have to write any code for now, we highly recommend creating a first project to ensure that VS Code works properly with the Java JDK:

1. Create a temporary folder to house this project anywhere you would like
    - For example, if you were using the file structure above, you might create a temporary folder under the `CS 201` folder called `Testing`
    - A temporary folder in your Desktop or Documents folder works as well!
2. Open VS Code, click `File > Open`, and navigate to the folder you just created.
3. Create a new file using `File > New File`. Save it (`File > Save`) as `HelloWorld.java`.
4. Paste the following code into `HelloWorld.java`:
    ```java
    public class HelloWorld {
      public static void main(String[] args) {
        System.out.println("Hello, world!"); 
      }
    }
    ```
5. Save `HelloWorld.java` and run it using either of the "Run" buttons highlighted below.
<div align="middle">
  <img src="images/vscode-runbuttons.png" width="600" />
</div>

6. You should see the integrated terminal window pop up, and your program should run and print `Hello, world!` into the terminal.

For a quick introduction to VS Code, you can skim [these](https://code.visualstudio.com/docs/introvideos/basics) official introductory resources. If you choose to do this, just watching the first one or two videos (less than 10 minutes) should be more than enough to give you a good idea of how it works.

## Installing Git and Configuring GitLab

Git is the most widely used version control system. Git allows you to keep track of the history of your projects and sync them with a remote copy on the Internet. We use Git in CompSci 201 and in many other courses at Duke. We use GitLab at https://coursework.cs.duke.edu as the online Git platform for you to get the starter code and upload your work. You'll authenticate using your NetID.

## Installing Git

**NOTE**: You can watch our UTAs go over the following Git installation process using Windows and Mac [here](#git-setup-videos) under the videos "Mac_SSH_Key" and "Windows_SSH_Key."

Head to https://git-scm.com/downloads and download the version of Git for your platform: Mac, Windows, Linux. Install this on your machine. Use default settings when prompted.

**Note**: On Mac you might see several options for downloading and installing Git. Any of them works, though we recommend using ***Homebrew***. To install Homebrew, run the following command in Terminal:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

After you’ve installed Homebrew, run the command `brew install git`.

### Setting Up Credentials in Git

Git can be used either on the command line (like Terminal in Mac and CMD on Windows), via the Git GUI, or via VS Code's built-in Git integration. **However, we strongly recommend that you use Git on the command line**. 

On a Mac, use the Terminal application, on Windows use either the Command Prompt that comes with the OS or the Git Bash Shell that is part of the Windows Git install.

In this shell/terminal type the commands below, but use your name and the ***firstname.lastname@duke.edu*** email address (with MI if applicable).

```bash
git config --global user.name "Owen Astrachan"
git config --global user.email "owen.astrachan@duke.edu"
```

### Generating SSH Key 

SSH is the protocol that Git uses to communicate to the remote server (GitLab in this case). You need to create an SSH key on your local machine, and then configure it in your settings on GitLab.

Refer to this documentation by GitLab on how to create an SSH key, specifically, the “***Generating a new SSH key pair***” section. Please use the **ED25519** command: https://coursework.cs.duke.edu/help/user/ssh.md#generate-an-ssh-key-pair

Again, you should use the ***firstname.lastname@duke.edu email address as your comment for your email***. Afterwards, when prompted to “Enter file in which to save the key” and “Enter passphrase”, ***we recommend saving the key at the default location and setting no passphrase (by just pressing Enter twice)***.
Note that for this step, Git Bash must be used on Windows. (The Command Prompt is still sufficient for other uses of Git.)

### Adding SSH Key to GitLab

Follow the steps in the next section in the GitLab documentation, “***Adding an SSH key to your GitLab account***”:
https://coursework.cs.duke.edu/help/user/ssh.md#add-an-ssh-key-to-your-gitlab-account

Note that you will use the commands shown in the documentation (subject to your OS) to copy the ***public*** part of your SSH key, ***which should start with “ssh-ed25519”***. You will then login to your GitLab account at https://coursework.cs.duke.edu, enter “Settings” from the top right corner, and then paste the public key by following the instructions in the documentation.

To verify that everything has been set up perfectly, use the following command:

`ssh -T git@coursework.cs.duke.edu`

If you see a welcoming message with your name or NetID, you’re done! Enjoy!

Note that if you see a similar prompt to this instead:
<div align="middle">
  <img src="images/git_host_authentication.jpg" width="300" />
</div>
Then that means that your computer doesn't recognize coursework.cs.duke.edu yet. Just reply yes to the prompt and then it should continue connecting.

## Git Setup Videos

### Mac
![](softwareInstallationVideos/Mac/videos/Mac_SSH_Key.mp4)

### Windows
![](softwareInstallationVideos/Windows/videos/Windows_SSH_Key.mp4)


