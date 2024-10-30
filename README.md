<h1>File Permissions In Linux</h1>


<h2>Description</h2>
I am a security professional at a large organization, primarily working with the research team. Part of my job is to ensure that users on this team have the appropriate permissions, which helps keep our system secure.
<br />
<br />
My task involves examining existing permissions on the file system to determine if they match the authorization that should be given. If they do not match, I need to modify the permissions to authorize the appropriate users and remove any unauthorized access.


<h2>Languages and Utilities Used</h2>

- <b>CLI</b>
- <b>Linux</b> 


<h2>Program walk-through:</h2>
<h3 align="center">Check file and directory details</h3>

<p align="center">
First, I listed the contents and permissions to the projects directory, which I used the <mark>ls -l</mark> command. I then listed the contents and permissions to any hidden files and subdirectories that exist, which I used the <mark>ls -a</mark> command. From the very beginning I could have used the <mark>ls -la</mark> command to show the contents and permissions for all available and hidden files and subdirectories.
<br/>
<br />
<img src="https://imgur.com/LMJXaxJ.png" height="80%" width="80%" alt="CLI File Permission Steps"/>
</p>
<br />
<br />

<h3 align="center">Describe the permissions string</h3>

<p align="center">
The permissions string is a 10-character representation. The first character indicates if the item is a directory (<mark>d</mark>) or a file (<mark>-</mark>). The next three characters specify the owner's permissions: <mark>r</mark> for read, <mark>w</mark> for write, <mark>x</mark> for execute, or <mark>-</mark> if the permission is not granted. The following three characters denote permissions for the group, and the last three characters represent permissions for others. Each set of three characters follows the same <mark>rwx</mark> structure, indicating read, write, and execute permissions for the respective user type.
<br/>
<br />
<img src="https://imgur.com/WtpURqc.png" height="80%" width="80%" alt="CLI File Permission Steps"/>
</p>
<br />
<br />

<h3 align="center">Change file permissions</h3>

<p align="center">
The organization does not allow for other to have writing permissions so I used the <mark>chmod o-w project_k.txt</mark> command to take away the write permission for owner type other on the file <mark>project_k.txt</mark>.

<br/>
<br />
<img src="https://imgur.com/1hJo8R6.png" height="80%" width="80%" alt="CLI File Permission Steps"/>
</p>
<br />
<br />

<h3 align="center">Change file permissions on a hidden file</h3>

<p align="center">
The research team has archived hidden file <mark>project_x.txt</mark> and should not allow anyone to have write permissions for it, but to only allow the user and group to read it. To do so I input the command <mark>chmod u=r,g=r .project_x.txt</mark>. By using <mark>=</mark> it will remove the write permission to both the user and group, and replace it with only the read permission for the user and group. 

<br/>
<br />
<img src="https://imgur.com/UUi1JXG.png" height="80%" width="80%" alt="CLI File Permission Steps"/>
</p>
<br />
<br />

<h3 align="center">Change directory permissions</h3>

<p align="center">
The files and directory in the projects directory belong to researcher2 user and only researcher2 should be allowed to access the drafts directory and its contents. I used the command <mark>chmod g-x drafts/</mark> to take away the permission for owner type group to execute files in drafts directory. This makes it so reasercher2 is the only one able to access the directory drafts and access its contents.

<br/>
<br />
<img src="https://imgur.com/QmfWZ2E.png" height="80%" width="80%" alt="CLI File Permission Steps"/>
</p>
<br />
<br />

<h3 align="center">Summary</h3>

<p align="center">
I identified several files and directories within the organization that had improper permissions. I reviewed and adjusted these permissions, ensuring that only authorized personnel have access. By implementing these changes, we have significantly reduced potential security risks, enhancing our overall data protection strategy.
<br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
