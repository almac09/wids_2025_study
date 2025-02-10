
# Git Issues

Large Excel files can definitely slow down a Git push, as they tend to have quite a bit of data and may not be optimally compressed.

**Git Large File Storage (LFS):** You can use Git LFS to store large files outside the regular Git repository. This can significantly speed up pushes for files like large Excel documents.

*"Git LFS is included in the distribution of Git for Windows. Alternatively, you can install a recent version of Git LFS from the Chocolatey package manager."* - [Git LF (README)](https://github.com/git-lfs/git-lfs?utm_source=gitlfs_site&utm_medium=installation_link&utm_campaign=gitlfs#installing)

```bash

git lfs install
git lfs track "*.xlsx", "*.csv", "*.csv.zip"
git add .gitattributes
git commit -m "Track all .xlsx, .csv, .csv.zip files with Git LFS"
git push origin main

```
## 1. Install Git LFS
To install Git LFS on your system, you use a package manager or download the installer from the official website.

```bash
git lfs install
```

## 2. Track .xlsx Files Recursively
To track all `.xlsx` & `.csv.zip` files across all subdirectories  in the repository, you use the following command. This ensures that Git LFS will manage all `.xlsx` & `.csv.zip` files in your repository, no matter where they are located.


```bash
git lfs track "*.xlsx", "*.csv"
```

The `"*.xlsx"` `"*.csv.zip"` wildcard pattern matches any file with the `.xlsx` extension in any subdirectory of the repository.


## 3. Add .gitattributes to Version Control
Git LFS modifies the .gitattributes file to specify which files should be tracked. After running the above command, you need to add the .gitattributes file to Git's staging area.

```bash

git add .gitattributes

```

## 5. Commit the Changes
Once the files are staged, you commit them to your local repository. This will save the .gitattributes file and the tracked .xlsx, csv & csv.zip files.

```bash
git commit -m "Track all .xlsx files with Git LFS"
```
The `-m` flag specifies the commit message.

## 6. Push Changes to Remote Repository
Finally, you push your committed changes to the remote Git repository. This includes uploading the `.xlsx`, `.csv`, `.csv.zip` files to Git LFS.

```bash
git push origin main
```

## 7. Merge local commits
This command merges the last 5 local commits
```bash
git reset --soft HEAD~5
```

## 8. Check the Remote Repository
Ensure that the push is being sent to the correct remote repository. You can check your remotes by running:

```bash
git remote -v
```
This will show you the remote repository URLs you're pushing to.

## **Check for Any Merge Conflicts** If there are any conflicts, Git might prevent the push until they are resolved. To check for conflicts:

```bash
git fetch upstream 
git merge upstream/main  # or the correct branch
```

## 9. how to force a push to work

```bash
# Configure Git to use the system CA certificates
# git config --global http.sslCAInfo "C:\Program Files\Git\mingw64\ssl\certs\ca-bundle.crt"
# git config --global http.sslCAInfo "C:\Users\alan.mcdonagh\AppData\Local\Programs\Git\mingw64\ssl\certs\ca-bundle.crt"

git config --global http.sslCAInfo "$env:LOCALAPPDATA\Programs\Git\mingw64\ssl\certs\ca-bundle.crt"

# As a last resort, disable SSL verification (not recommended)
git config --global http.sslVerify false

# Push your changes to the upstream repository
git push -u upstream main
```