# merge-3-repos-into-1
Import other repos into 1, creating subfolders for each and keeping history. Below is the literal example for how I moved javascript-exercises. Same applied for the other repos.

You have to create another branch on which you'll add the repo you want to add to the other repo.
Then you will move everything on the branch in a subfolder.
That subfolder will be merged into main repo.
Push and done.

SCRIPT.SH


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cd merge-3-repos-into-1/
ls
git remote add javascript-exercises https://github.com/qSharpy/javascript-exercises
git fetch javascript-exercises
git checkout -b javascript-exercises javascript-exercises/master
mkdir javascript-exercises
ls
git mv -k * javascript-exercises/
ls -ltrha
git mv .gitignore javascript-exercises/
ls -ltrha
git commit -m "Moved all javascript-exercises into subfolder"
git checkout main
git merge javascript-exercises --allow-unrelated-histories
git status
git commit -m "Merged with javascript-exercises repo"
ls
git push
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git clone YOUR MAIN REPO LINK
cd YOUR-MAIN-REPO/
git remote add REPO1 LINK-TO-REPO1
git fetch <REPO1>
git checkout -b REPO1 REPO1/master
mkdir REPO1
git mv -k * REPO1/
ls -ltrha
#don't forget to move .files. check if you have any .files not moved with
ls -ltrha
#if you do have .files in the folder, move tgem with:
git mv .NAME-OF-FILE1 .NAME-OF-FILE2 REPO1/
git commit -m "Moved all REPO1 files into subfolder"
git checkout main
git merge REPO1 --allow-unrelated-histories
git status
git commit -m "Merged with REPO1 repo"
ls
git push
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
