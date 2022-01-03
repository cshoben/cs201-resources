# APT Workflow
APTs are small-scale “problem sets” where you have to write a Java method to solve a particular problem. Unlike assignments (projects), APTs do not come with starter codes for you to clone and import (though each APT problem has an empty method stub as a starting point). You will have to create Java folders in which you will write and run code using VS Code.

We recommend creating a new project for each APT set, e.g. the project can be called “APT1” which contains code for each problem in this APT; later you can create a new project called “APT2”, etc.

Note: You can also create a Git repo for each APT, so that you can backup your work in the local IntelliJ project to a remote repository on GitLab. While it’s not required, we strongly recommend doing so as it allows you to view the file history easily, saves your work in case of hardware failures, and lets UTAs view your full code more conveniently. If you wish to do so, see instructions below before creating the project in IntelliJ.

To create a new project in IntelliJ:

Click on “Create New Project” from the welcome screen. 
IntelliJ will now ask you to choose the language and the SDK. Typically, the “Project SDK” dropdown menu should have a default option “15” [or any version of Java (at least 11)] which looks like the one below. (If you do not see such an option or only has “<No SDK>” in the dropdown menu, refer to the Troubleshooting Document.)



Click “Next” twice until you reach a screen with the project name and location settings. You will give each project a name, and we recommend storing the project in a subdirectory under your CS201 workspace, as mentioned above. Do NOT set the project location to be the “CS201” directory itself!


(If you have already created a GitLab repo and cloned it to your computer, you should choose the project location to be where the empty Git repo is. You will get a warning that the target directory already exists, just ignore it.)

You will then enter the IntelliJ workspace. Clicking the “Project” button in the left sidebar will show you the file hierarchy. 
Creating New Java Classes
You can create a new Java class (file) in the src folder. All Java classes should be placed in the src folder.

Right clicking on the directory, then choose “New” - “Java Class”:



When creating Java classes for APTs, the APT problem statement should have provided you a name for the class as well as some stub code for you to get started, as shown below. Type the same class name in the “New Java Class” window.
If an assignment/project asks you to create a Java class, the name of the class would have been given in the instructions.
  

You will then be brought to the new Java file ending with “.java”. For APTs, replace the file’s contents with the given code from the APT.

Now you can start developing your code. (If you get a red error like shown above, don’t worry. You should be able to resolve the error once you put in a return statement.)

Running your code
You can only run a Java class if it has a main method (more on that later in the course). For assignments, we will most likely provide a class with a main method for you. For APTs, you typically do not need to execute any files you create (but you can still create a main method to debug your APT). 

To run a Java class, from the Run menu choose “Run...” (with the ellipsis), and then choose the class that you want to execute:



Once you do that for the first time, IntelliJ will remember which class you executed. Subsequently, you can choose the first option “Run” (without the ellipsis), and IntelliJ will run the most recently executed class - regardless of which file you’re currently editing - until you use “Run...” and choose a different class to run. This means if you run class A first and then open another class B and make changes, the option “Run” without ellipsis will still run class A, even if the window for B.java is currently active.
(Optional) Creating a main method for APTs
As mentioned above, you do NOT need to run your code for APTs; as such, a main method is not required. Nevertheless, if you’re having errors, having a main method is extremely helpful for debugging your code.

To create a main method, add the following method within the class (it should not be nested within another method):

public static void main(String[] args) {
    // code here
}

And then replace // code here with code that you want to execute.

For APTs, you typically want to run the method you wrote on some specific inputs. Thus, your main method will mainly consist of the following steps:
Declaring input variables (parameters of the APT method) and initializing them with values
Creating a new object of the APT class by using new APTNameHere()
Calling the method and storing the return value in a variable
Print out the return value using System.out.println()

As a concrete example, here’s a Java class for the the Starter APT with a main method for debugging:
public class Starter {
public int begins(String[] words, String first) {
// replace this code 
return 0;
}
public static void main(String[] args) {
    String[] words = {"easy", "lies", "the", "head", "that", "wears", "yellow"};
    String first = “e”;
    Starter obj = new Starter();
int ans = obj.begins(words, first);
System.out.println(ans);
}
}

Note that if the return value is an array, you can use Arrays.toString to print out the contents of the array:

    // a is an array
    System.out.println(Arrays.toString(a));

Remember you can use a main method to test you code, but it must be removed or commented out before you submit it to the APT tester.
(Optional) Creating a Git Repo for APTs
Using Git for APTs is not required, but we recommend that you create a Git repo for APTs and push your work to GitLab regularly. This helps preserve your work in a catastrophic computer failure.
Creating a Git repo without an existing IntelliJ project
The following steps are for starting afresh on the APT, when you don’t have any files on your computer. This is the recommended workflow: create a repository on GitLab first, clone the empty repo to your computer, then create an IntelliJ project there.

Create a new repository in GitLab: https://coursework.cs.duke.edu/projects/new
Remember to make your repository private!!!
Open a Terminal or CMD/Git Bash shell, and use the cd command to navigate to where you want to save the project, typically your CS201 workspace.
Once you’re in the directory, type

    git clone <your-project-URI>

Replacing <your-project-URI> with the SSH URI of your GitLab project (obtained from the “Clone” option on your project’s home page).
The git clone command should have created a new directory in your CS201 workspace for the Git repo. Create a new IntelliJ project in this directory.

When you make changes (e.g. made progress on a few APT problems), remember to push them to Git regularly using the standard command sequence mentioned above.

Creating a Git repo with an existing IntelliJ project on the local machine
This section is for the case where you already have some work done on your computer, but now want to create a GitLab repository and upload your work there.

Create a new repository in GitLab: https://coursework.cs.duke.edu/projects/new
Remember to make your repository private!!!
Open a Terminal or CMD/Git Bash shell, and use the cd command to navigate to your directory. This should be the project directory, not the general CS201 workspace. 
Make sure you’re in the root folder of your project: it should contain a src subdirectory which has all the Java files.
Once you’re in the directory, use the following commands:

git init
git remote add origin <your-project-URI>
git add .
git commit -m "Initial commit"
git push -u origin master

Replacing <your-project-URI> with the SSH URI of your GitLab project (obtained from the “Clone” option on your project’s home page). These commands will initialize the directory as a Git repository and link it to the remote repo.
Note the “-u origin master” arguments for git push. These are necessary in this particular scenario, as they tell Git which remote repository and branch to push to.

You should now be able to see contents of the repository on GitLab. When you make additional changes, you can use use the standard command sequence for pushing, without the “-u origin master” part.
