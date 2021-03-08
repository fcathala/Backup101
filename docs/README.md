# backup101

*Ultra-simple backup utility - Fabrice Cathala 🐸*

---

backup101 is an ultra-simple backup utility that generates full copies of the files and folders you indicate into a folders structure going to up to 898 versions. This should be way enough to revert any project, should it be coding or documenting or anything to do with computer files, to a previous state.

The clue is on its *simplicity* to work with and could not be compared with a full-blown version control system such as [GitHub](https://github.com/). It only provides a security (backup) when working on projects single-handedly. It does NOT offer merge management, distributed repository, nor any publication or add-ons coming with all popular VCS. It does allow to go back in time and play around with good versions from the past. The actual restore operation is left to the user discretion as well as the frequency of the backups.

⚠️ Note that *speed* is NOT the name of the game here, again it's all about *simplicity*. Simplicity is a key weapon as far as computer security is concerned! When dealing with many versions, say more than 200 folders, backup101 can take a couple of minutes to complete one backup activity.

## First Installation

From the [GitHub repository](https://github.com/fcathala/backup101) click on the green button "Code" and download the whole package. Chose which directory you should use (Mac or PC). This folder is the one containing backup101 and must be copied within your project folder. I usually rename it to "*backup*" but you are not obliged to do so.

## Project Configuration

You are expected to be dealing with a Project folder first. This folder is expected to contain important (and less important) files and folers. Backup101, once configured, will aim at simplifying backup copies and manage their history for you. "101" is the most recent backup, "999" is the oldest.

```
C:\USERS\<YOUR_NAME>\<PROJECT_NAME>
│   Hello_0.txt
├───Boom
│       Hello.txt
├───Folder_1
│       Hello_1.txt
├───Folder_2
│      Hello_2.txt
│
├───backup
│   │   backup101.cmd
│   ├───backup.101
│   │   │   Hello_0.txt
│   │   ├───Folder_1
│   │   │       Hello_1.txt
│   │   └───Folder_2
│   │           Hello_2.txt
│   │
│   ├───backup.102
│   │   │   Hello_0.txt
│   │   ├───Folder_1
│   │   │       Hello_1.txt
│   │   └───Folder_2       
│   │           Hello_2.txt
│   │
│   ├───...
```

At the end of the script, should it be for the PC or Mac platform, you should manually edit what are the actual files and folders of interest. backup101 will allow you recover one day from the backups you are taking. **Please do NOT forget this one-off step**

```
	Rem ===========================================================
	Rem Please edit manually below what the source actually is...
	Rem ===========================================================

	Xcopy ..\*.* backup.101\ /V /I
	Xcopy ..\Folder_1 backup.101\Folder_1 /V /I
	Xcopy ..\Folder_2 backup.101\Folder_2 /V /I
```

## Execution

When correctly installed, launching a backup is as simple as executing a script (backup101.sh on a Mac, backup101.cmd on a PC). Then, when needed (hopefully never), you can go and browse your backup folders collection to pull the file(s) you need from a local backup done at a certain time (backup.101, backup.102, etc...).

Have fun!

## Useful Links
* [Defining a backup strategy](https://searchdatabackup.techtarget.com/definition/backup)
* [The interest of testing in backup planning](https://searchdatabackup.techtarget.com/tip/Top-3-backup-and-recovery-requirements-for-data-protection)
