# Git Troubleshooting Guide

<details>
<summary>When I open projects in IntelliJ, lots of words are red, and I can't run my code</summary>
<br>

- The culprit is likely that the student **has not set up a SDK and configured their code to be read as Sources Root**. To resolve this issue, go to File &rarr; Project Structure &rarr; Projects and set up the SDK to the most recent version of Java. After applying the SDK changes, right click the `src` folder and navigate to Mark Directory as &rarr; Sources Root.

- If this oddly does not resolve the issue, close and reopen IntelliJ. If that does not work, go to File &rarr; Invalidate Caches/Restart &rarr; Invalidate and Restart.
</details>

<details>
<summary>I get red squiggly lines saying “Cannot access &lt;interface&gt;” after opening my project, even though that interface was provided in the starter code and the file is present in IntelliJ</summary>
<br>

- The issue is often resolved by closing and reopening IntelliJ. If that does not work, go to File &rarr; Invalidate Caches/Restart &rarr; Invalidate and Restart.

</details>

<details>
<summary>When trying to install Git, I am having difficulties with Homebrew</summary>
<br>

- If the student has already successfully installed Homebrew, have them run the command `brew install git` (no $). If that fails, have them reinstall Homebrew and then repeat the process.

- If they are having difficulty installing Homebrew, a general rule of thumb is to make sure that the student's OS is up to date. If the student is not on the most recently available OS, have them update in order to increase chances of success. Afterwards, run the commands supplied on the Homebrew page again.

- If the student is having any difficulty with their `bin` folder not existing or any other fatal directory issues, refer the student to OIT; their machine needs serious maintenance and restructuring.

</details>

<details>
<summary>When I try to do anything Git related, my computer asks me for a password</summary>
<br>

- If the student has been able to use Git successfully in the past, then they **cloned with HTTPS instead of SSH**. To resolve this issue, have them save the code they have written so far locally (*not in IdeaProjects*), repull the project via SSH, and then replace the files in their new starter code with their locally stored code.

- If the student has never used Git successfully, then they need to **reconfigure their SSH key**. When doing so, walk through them through the steps detailed in the key configuration guide [here](https://docs.google.com/document/d/1m9B4q1j-umopgBUUFUTiuMmLufAuqBa6X0ul_FlQHos/edit) and lend attention to two important details:

    1. The student must set save the key to a default location (press "Enter" once) and then set a default password (press "Enter" twice)

    2. When linking the key to GitLab, the student must access their account at `coursework.cs.duke.edu` and login via Shibboleth. They should *not* login in at `gitlab.oit.duke.edu` with a username and password.

- If the student is still unable to configure their SSH key after following the above steps, then they likely *have another primary SSH key for personal/professional use*. To work around this, run the following set of UNIX commands and then reattempt linking the SSH key to GitLab:

```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_ed25519
```

</details>


<details>
<summary>When I try pushing anything to Git, the process fails or some error message appears</summary>
<br>

- First, check whether the student **has been successful in the past with Git**. If they have not, run a quick diagnostic to see if they have configured their SSH key properly by running `ssh -T git@coursework.cs.duke.edu`.

- Next, ask the student if they forked the repository, and if they are not sure, go to the GitLab page and check if they did so. If the student did not fork the repository, have them save their code in a secure place, delete the repository from IdeaProjects, fork the repository, and then repull it. 

- Otherwise, make sure that the student is in the proper directory by having them run the command `pwd` in their terminal. If they are not, make sure that they follow the proper file path and eventually `cd IdeaProjects` and then `cd project_name`.

- From here, make sure that the student writes the following three UNIX commands while in the proper directory:

```bash
git add .
git commit -m "write comment here"
git push
```

- Now suppose the student follows all of those steps, yet they receive the following error message

```bash
/Users/student/.config/git/ignore: Permission denied
Users/student/.config/git/attributes: Permission denied
```

This means that the student has certain permission errors on their machine. To resolve this issue, have the student return to their home directory by running `cd ~`,
 run `sudo chmod 755 .config`, and then type in their password for their device.

</details>

<details>
<summary>My partner and I are working on the same repository, and we're having trouble pushing code</summary>
<br>

- The code is being rejected because their local commits (changes) are not in sync with the remote history. This happens if both people are working on the same repo on different computers, or if several people are collaborating on the same repository. If computer A pushes changes to GitLab, and computer B also pushes, GitLab could not tell whether it should accept A's or B's changes, so the push will be rejected.

- To resolve this, they will need to `git pull` from remote. To do so, they should run the following set of commands:

```bash
git pull
//potentially resolve merge conflict manually
git push
```

- In the event that Git is not able to automatically resolve the issue, the student will have to resolve the issue manually. Running the three `git add .`, `git commit -m "comment"`, and `git push` commands should resolve the issue.

- If you would like to learn more about Git merge conflicts, feel free to watch the video [here](https://duke.zoom.us/rec/play/SaYwuDmE_e1ktnTdXyZFlUB4Je0jAp90JJsYpv6nGO_6xgn2eTFqcR9poqNQpKOqlswpyR54w5lkpw.jhA1Dob-5DIFNjdB?continueMode=true&_x_zm_rtaid=WRHafTqZSU-Bw07DppwXJg.1614437909258.5f6f5e1afb9e427d7e1e52e2574318f9&_x_zm_rhtaid=958) for your own edification. 

</details>


