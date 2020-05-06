**How to setup a Jenkins production and testing pipeline using docker..!!**

Assumptions: Jenkins And Docker are installed in RHEL OS

Jenkins is added in /etc/sudoers file and given all the permissions.

**PART 1 (Basic SETUP)**

 1. Create a folder on your Desktop

2. Create a index.html file and write something it.

3. Open Git bash where your file is located

4. Create a git repository using (git init)

5. Now create development branch by typing:

\&lt;Git branch development\&gt;

To check this branch type git checkout \&lt;branchname\&gt;

Here my branch name is developer

Screen will look something like this

![](RackMultipart20200506-4-15rwxm_html_77266aa199b39b64.png)

7. Edit your code in this branch

8. Add and commit the code

Git add.

Git commit -m &quot;message&quot;

Git checkout master

9. Git push –all or you can create a Hook&#39;s (post-commit) in which you can add the command git push. Which will make it automatically push after commit is executed.

![](RackMultipart20200506-4-15rwxm_html_2e56fd9e6cf4fbb3.png)

**PART 2 (JENKINS SETUP)**

Step 1:

Create Job1 with following configuration

![](RackMultipart20200506-4-15rwxm_html_92a18cb5e9529f62.png)

![](RackMultipart20200506-4-15rwxm_html_b2e39ca5e42d36cc.png)

Save the job

STEP 2:

Create another job for production server: job2

![](RackMultipart20200506-4-15rwxm_html_17fd575119ad9db8.png)

![](RackMultipart20200506-4-15rwxm_html_1a56a20a4bf67722.png)

Save the job

STEP 3

For Development Environment

Create a job name gitup-test.

![](RackMultipart20200506-4-15rwxm_html_2c08d2ea82a0faf4.png)

#REPLACE the master with your development branch

![](RackMultipart20200506-4-15rwxm_html_aa42b94a9616337d.png)

![](RackMultipart20200506-4-15rwxm_html_7b0b5b10f084807b.png)

Step 4

Create a job QA-approved

Don&#39;t forget to give your credentials here

![](RackMultipart20200506-4-15rwxm_html_9560be36192aa78f.png)

# go to advanced post build section

![](RackMultipart20200506-4-15rwxm_html_e6ccddbabbc86ec7.png)

This is how the index page in branch looks

![](RackMultipart20200506-4-15rwxm_html_256f9254b2696a1c.png)

This is what development server looks like

![](RackMultipart20200506-4-15rwxm_html_fb7b0cd2d0d8bc33.png)