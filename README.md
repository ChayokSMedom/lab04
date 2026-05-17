# Отчёт:

```
reyne@reyne-VirtualBox:~$ open https://git-scm.com
reyne@reyne-VirtualBox:~$ update.go:85: cannot change mount namespace according to change mount (/var/lib/snapd/hostfs/usr/local/share/doc /usr/local/share/doc none bind,ro 0 0): cannot write to "/var/lib/snapd/hostfs/usr/local/share/doc" because it would affect the host in "/var/lib/snapd"
update.go:85: cannot change mount namespace according to change mount (/var/lib/snapd/hostfs/usr/share/gimp/2.0/help /usr/share/gimp/2.0/help none bind,ro 0 0): cannot write to "/var/lib/snapd/hostfs/usr/share/gimp/2.0/help" because it would affect the host in "/var/lib/snapd"
update.go:85: cannot change mount namespace according to change mount (/var/lib/snapd/hostfs/usr/share/gtk-doc /usr/share/gtk-doc none bind,ro 0 0): cannot write to "/var/lib/snapd/hostfs/usr/share/gtk-doc" because it would affect the host in "/var/lib/snapd"
update.go:85: cannot change mount namespace according to change mount (/var/lib/snapd/hostfs/usr/share/xubuntu-docs /usr/share/xubuntu-docs none bind,ro 0 0): cannot write to "/var/lib/snapd/hostfs/usr/share/xubuntu-docs" because it would affect the host in "/var/lib/snapd"
libpxbackend-1.0.so: cannot open shared object file: No such file or directory
Failed to load module: /home/reyne/snap/firefox/common/.cache/gio-modules/libgiolibproxy.so
Gtk-Message: 23:31:25.411: Not loading module "atk-bridge": The functionality is provided by GTK natively. Please try to not load it.

reyne@reyne-VirtualBox:~$ export GITHUB_USERNAME=reyne
reyne@reyne-VirtualBox:~$ export GITHUB_EMAIL=medvedevachm@gmail.com
reyne@reyne-VirtualBox:~$ alias edit=nano
reyne@reyne-VirtualBox:~$ cd ${GITHUB_USERNAME}/workspace
reyne@reyne-VirtualBox:~/reyne/workspace$ source scripts/activate
reyne@reyne-VirtualBox:~/reyne/workspace$ mkdir ~/.config
mkdir: /home/reyne/.config: File exists
reyne@reyne-VirtualBox:~/reyne/workspace$ cat > ~/.config/hub <<EOF
github.com:
- user: ${GITHUB_USERNAME}
  oauth_token: ${GITHUB_TOKEN}
  protocol: https
EOF
reyne@reyne-VirtualBox:~/reyne/workspace$ git config --global hub.protocol https
reyne@reyne-VirtualBox:~/reyne/workspace$ mkdir projects/lab02 && cd projects/lab02
mkdir: projects/lab02: File exists
reyne@reyne-VirtualBox:~/reyne/workspace$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: will change to "main" in Git 3.0. To configure the initial branch name
hint: to use in all of your new repositories, which will suppress this warning,
hint: call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
hint:
hint: Disable this message with "git config set advice.defaultBranchName false"
Initialized empty Git repository in /home/reyne/reyne/workspace/.git/
reyne@reyne-VirtualBox:~/reyne/workspace$ git config --global user.name ${GITHUB_USERNAME}
reyne@reyne-VirtualBox:~/reyne/workspace$ git config --global user.email ${GITHUB_EMAIL}
reyne@reyne-VirtualBox:~/reyne/workspace$ git remote add origin https://ChayokSMedom:TOKEN@github.com/ChayokSMedom/lab02.git
reyne@reyne-VirtualBox:~/reyne/workspace$ git pull origin master
fatal: couldn't find remote ref master
reyne@reyne-VirtualBox:~/reyne/workspace$ pwd
/home/reyne/reyne/workspace
reyne@reyne-VirtualBox:~/reyne/workspace$ cd ~/reyne/workspace/projects/lab02
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git log
fatal: your current branch 'master' does not have any commits yet
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git add .
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git commit -m "Initial commit"
On branch master

Initial commit

nothing to commit (create/copy files and use "git add" to track)
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git pull origin master
fatal: couldn't find remote ref master
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git push -u origin master
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab02.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git push -u origin main
error: src refspec main does not match any
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab02.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ echo "*build*/" > .gitignore
echo "*install*/" >> .gitignore
echo "*.swp" >> .gitignore
echo ".idea/" >> .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ ls -la
total 16
drwxrwxr-x 3 reyne reyne 4096 May 17 23:39 .
drwxrwxr-x 3 reyne reyne 4096 May 17 23:06 ..
drwxrwxr-x 6 reyne reyne 4096 May 17 23:36 .git
-rw-rw-r-- 1 reyne reyne   33 May 17 23:39 .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ pwd
/home/reyne/reyne/workspace/projects/lab02
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git init
Reinitialized existing Git repository in /home/reyne/reyne/workspace/projects/lab02/.git/
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git add .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git commit -m "Add .gitignore"
[master (root-commit) a8b7272] Add .gitignore
 1 file changed, 4 insertions(+)
 create mode 100644 .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git remote add origin https://github.com/ChayokSMedom/lab02.git
git branch -M main
git push -u origin main
error: remote origin already exists.
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 243 bytes | 243.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/ChayokSMedom/lab02.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git pull origin master
fatal: couldn't find remote ref master
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git log
commit a8b7272ff23df9fd48d01dfae0a5c92306174036 (HEAD -> main, origin/main)
Author: reyne <medvedevachm@gmail.com>
Date:   Sun May 17 23:41:13 2026 +0300

    Add .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git pull origin main
From https://github.com/ChayokSMedom/lab02
 * branch            main       -> FETCH_HEAD
Already up to date.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ mkdir sources
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ mkdir include
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ mkdir examples
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ cat > include/print.hpp <<EOF
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$  cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ cat > examples/example2.cpp <<EOF
#include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	examples/
	include/
	sources/

nothing added to commit but untracked files present (use "git add" to track)
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git add .
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$  git commit -m"added sources"
[main e4f88af] added sources
 4 files changed, 32 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git push origin master
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab02.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ git push origin main
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 2 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (9/9), 894 bytes | 447.00 KiB/s, done.
Total 9 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/ChayokSMedom/lab02.git
   a8b7272..e4f88af  main -> main
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ cd ~/workspace/
bash: cd: /home/reyne/workspace/: No such file or directory
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab02$ cd /home/reyne/reyne/workspace
reyne@reyne-VirtualBox:~/reyne/workspace$ cd ~/workspace/
bash: cd: /home/reyne/workspace/: No such file or directory
reyne@reyne-VirtualBox:~/reyne/workspace$ pwd
/home/reyne/reyne/workspace
reyne@reyne-VirtualBox:~/reyne/workspace$ ln -s ~/reyne/workspace ~/workspace
reyne@reyne-VirtualBox:~/reyne/workspace$ cd ~/workspace/
reyne@reyne-VirtualBox:~/workspace$  export LAB_NUMBER=02
reyne@reyne-VirtualBox:~/workspace$ git clone https://github.com/tp-labs/lab${LAB_NUMBER}.git tasks/lab${LAB_NUMBER}
Cloning into 'tasks/lab02'...
remote: Enumerating objects: 96, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 96 (delta 0), reused 1 (delta 0), pack-reused 93 (from 1)
Receiving objects: 100% (96/96), 1.29 MiB | 4.20 MiB/s, done.
Resolving deltas: 100% (28/28), done.
reyne@reyne-VirtualBox:~/workspace$ mkdir reports/lab${LAB_NUMBER}
reyne@reyne-VirtualBox:~/workspace$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
reyne@reyne-VirtualBox:~/workspace$ cd reports/lab${LAB_NUMBER}
reyne@reyne-VirtualBox:~/workspace/reports/lab02$ edit REPORT.md
reyne@reyne-VirtualBox:~/workspace/reports/lab02$ gist REPORT.md
gist: (WARNING) fread failed (command) on CGM file REPORT.md
gist: (WARNING) BEGIN METAFILE element missing
gist: (WARNING) REPORT.md is not a binary CGM, cannot open
gist> 
```
