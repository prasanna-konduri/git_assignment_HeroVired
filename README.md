# Git Assignment HeroVired
## Introduction:
  The repository aims to demonstrate usage and implementation of key git hub features like ease working on different branches and usage of various git hub commands. Also gives a breif introduction to the concept of git hub large file storage and its basic usage. 
  
## Features:
  This Repository contains 3 case studies related to git hub
  1. Working on a feature Implementation and bugfixes at the same time seemlessly
  2. Woring with GLFS.
  3. The demonstarion of 'git stash' when working on diffrent branches

## Prerequisites:
  - git version 2.39.3 
  - Python 3.12.4
  - Git LFS

## Implementation:
1. Calculator plus app:
   - Created a git repo with name 'git_assignment_HeroVired'.
   - Cloned the repository to my local system using the below command
     ```sh
       git clone <repository-link> 
     ```
   - created a dev branch
     ```sh
       git checkout -b dev
      ```
   - Pasted the given code in the dev branch and pushed it to remote
     ```sh
       git add .
       git commit -m "<commit message>"
       git push origin dev
      ```
   - Relased V1 of the project
   - Added a team member as contributor
   - Created a branch to implement square root feature from dev branch
     ```sh
       git checkout -b feature/sqrt
      ```
   - While working on the feature encounterd a bug in main so stashed the changes and created a branch for bug fix
     ```sh
       git stash
       git checkout main
       git checkout -b bug_fix
      ```
   - Fixed the bug and created a pull request to merge the branch to main branch
   - After the bugfix switched back to feature branch
     ```sh
       git checkout feature/sqrt
       git stash apply
     ```
   - Implemented squre root feature and pushed the code to remote
     ```sh
       git add .
       git commit -m "<commit message>"
       git push origin feature/sqrt
     ```
   - Created a pull request to merge the feature branch to dev and asked a review from the collaborator.
   - After the approval and merge of the reviwer merged from dev branch to main branch.
   - Released V2 of the app.
     
2. Git Large File System:
  - To implement the LFS first install the git-lfs into your local system. For Mac users - Navigate to git-lfs.com and click Download. Alternatively, you can install Git LFS using a package manager:
    1. To use Homebrew, run brew install git-lfs.
    2. To use MacPorts, run port install git-lfs.
  - Verify that the installation was successful:
    ```sh
      git lfs install
      >Git LFS initialized.
    ```
  - Then go to local git repository where the large files are located to upload.Created a branch named 'lfs' using git checkout command.
    ```sh
         git checkout -b lfs
    ```
  - Congigure the lfs with the file type you want upload with below command
    ```sh
         git lfs track "*.pdf"
    ```
  - Add a file to the repository matching the extension you've associated
     ```sh
         git add path/to/file.pdf
     ```
  - Commit the file and push it to lfs branch
    ```sh
      git commit -m "<commit message>"
      git push origin lfs
    ```
  - cloned the repo in another machine for testing.
    
3. Git Stash implementation:
  - Created a branch 'geometric-calculator'. added the code given and pushed to remote.
    ```sh
      git checkout -b geometric-calculator
      git add .
      git commit -m "<commit message>"
      git push origin geometric-calculator
    ```
  - Created a feature branch 'feature/circle-area' from geometric-calculator branch.
     ```sh
      git checkout -b feature/circle-area
     ```
  - Made few changes to the code. stashed them using 'git stash' in circle area branch and checked if the working directory is clean with below commands.
    ```sh
      git stash
      git status
    ```
  - Checked out to geometric-calculator branch. From there created a new feature branch 'feature/rectangle-area'
    ```sh
      git checkout geometric-calculator
      git checkout -b feature/rectangle-area
    ```
  - Worked on rectangle area and stashed the changes and moved to circle area branch and checked if the working directory is clean with below commands.
    ```sh
      git stash
      git status
    ```
  - Again checked out to circle area branch. Checked the list of stashes applied the specific stash, committed and pushed circle area branch to remote.
     ```sh
      git checkout feature/circle-area
      git stash list
      git stash apply 1
      git add .
      git commit -m "<commit message>"
      git push origin feature/circle-area 
    ```
  - Switched to rectangle area branch listed and applied specific stash related to that branch completed the implementation and pushed to remote.
     ```sh
      git checkout feature/rectangle-area
      git stash list
      git stash apply 0
      git add .
      git commit -m "<commit message>"
      git push origin feature/reactnagle-area 
    ```
  - Created pull requests for both the branches to merge in to geometric-calculator branch. Asked for review.
  - Once the reviewr approved and merged the branches, created a pull request from geometric-calculator to dev branch and from dev to main branch.
  
    
