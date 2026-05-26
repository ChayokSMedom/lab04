# Отчёт:
я просто копировала и вставила весь терминал который ушёл на эту работу

```
reyne@reyne-VirtualBox:~$ export GITHUB_USERNAME=reyne
reyne@reyne-VirtualBox:~$ cd ~/workspace
reyne@reyne-VirtualBox:~/workspace$ export GITHUB_USERNAME=ChayokSMedom
reyne@reyne-VirtualBox:~/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/lab04
Cloning into 'projects/lab04'...
remote: Enumerating objects: 21, done.
remote: Counting objects: 100% (21/21), done.
remote: Compressing objects: 100% (15/15), done.
Receiving objects: 100% (21/21), 9.98 KiB | 9.98 MiB/s, done.
Resolving deltas: 100% (3/3), done.
remote: Total 21 (delta 3), reused 17 (delta 2), pack-reused 0 (from 0)
reyne@reyne-VirtualBox:~/workspace$ cd projects/lab04
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git remote remove origin
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab04
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ mkdir -p .github/workflows
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ 
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cat > .github/workflows/ci.yml << 'EOF'
name: CI

on:
  push:
    branches: [ main, master ]
  pull_request:
    branches: [ main, master ]
  workflow_dispatch:  # позволяет запускать вручную

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Configure CMake
      run: |
        mkdir -p build
        cmake -H. -Bbuild -DCMAKE_INSTALL_PREFIX=_install
    
    - name: Build
      run: cmake --build build
    
    - name: Install
      run: cmake --build build --target install
    
    - name: Test
      run: |
        cd build
        ctest --output-on-failure
      continue-on-error: true
EOF
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cd ~/workspace/projects/lab04
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ mkdir -p .github/workflows
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ 
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cat > .github/workflows/ci.yml << 'EOF'
name: CI

on:
  push:
    branches: [ main, master ]
  pull_request:
    branches: [ main, master ]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Configure CMake
      run: cmake -H. -Bbuild -DCMAKE_INSTALL_PREFIX=_install
    
    - name: Build
      run: cmake --build build
    
    - name: Install
      run: cmake --build build --target install
EOF
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ ls -la .github/workflows/
total 12
drwxrwxr-x 2 reyne reyne 4096 May 18 10:49 .
drwxrwxr-x 3 reyne reyne 4096 May 18 10:49 ..
-rw-rw-r-- 1 reyne reyne  412 May 18 10:55 ci.yml
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git add .github/workflows/ci.yml
git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   .github/workflows/ci.yml

reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git commit -m "Add GitHub Actions workflow"
[main cd774b4] Add GitHub Actions workflow
 1 file changed, 23 insertions(+)
 create mode 100644 .github/workflows/ci.yml
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
Enumerating objects: 26, done.
Counting objects: 100% (26/26), done.
Delta compression using up to 2 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (26/26), 10.50 KiB | 2.10 MiB/s, done.
Total 26 (delta 4), reused 20 (delta 3), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), done.
remote: error: GH013: Repository rule violations found for refs/heads/main.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:32
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:320
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:416
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab04/security/secret-scanning/unblock-secret/3DtAu8yfiLb2040VBjXEGcj06AN
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:324
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:326
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab04/security/secret-scanning/unblock-secret/3DtAu4esAORaczUYAVZnuw7MMAX
remote:     
remote: 
remote: 
To https://github.com/ChayokSMedom/lab04
 ! [remote rejected] main -> main (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab04'
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ nano README.md
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
Enumerating objects: 26, done.
Counting objects: 100% (26/26), done.
Delta compression using up to 2 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (26/26), 10.50 KiB | 2.10 MiB/s, done.
Total 26 (delta 4), reused 20 (delta 3), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), done.
remote: error: GH013: Repository rule violations found for refs/heads/main.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:32
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:320
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:416
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab04/security/secret-scanning/unblock-secret/3DtAu8yfiLb2040VBjXEGcj06AN
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:324
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:326
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab04/security/secret-scanning/unblock-secret/3DtAu4esAORaczUYAVZnuw7MMAX
remote:     
remote: 
remote: 
To https://github.com/ChayokSMedom/lab04
 ! [remote rejected] main -> main (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab04'
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
Enumerating objects: 26, done.
Counting objects: 100% (26/26), done.
Delta compression using up to 2 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (26/26), 10.50 KiB | 3.50 MiB/s, done.
Total 26 (delta 4), reused 20 (delta 3), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), done.
remote: error: GH013: Repository rule violations found for refs/heads/main.
remote: 
remote: - GITHUB PUSH PROTECTION
remote:   —————————————————————————————————————————
remote:     Resolve the following violations before pushing again
remote: 
remote:     - Push cannot contain secrets
remote: 
remote:     
remote:      (?) Learn how to resolve a blocked push
remote:      https://docs.github.com/code-security/secret-scanning/working-with-secret-scanning-and-push-protection/working-with-push-protection-from-the-command-line#resolving-a-blocked-push
remote:     
remote:     
remote:       —— GitHub Personal Access Token ——————————————————————
remote:        locations:
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:324
remote:          - commit: cc8566bbf9996534f2b265e22ff3bbc4c49098ff
remote:            path: README.md:326
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab04/security/secret-scanning/unblock-secret/3DtAu4esAORaczUYAVZnuw7MMAX
remote:     
remote: 
remote: 
To https://github.com/ChayokSMedom/lab04
 ! [remote rejected] main -> main (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab04'
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': ChayokSmedom
Password for 'https://ChayokSmedom@github.com': 
Enumerating objects: 26, done.
Counting objects: 100% (26/26), done.
Delta compression using up to 2 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (26/26), 10.50 KiB | 2.62 MiB/s, done.
Total 26 (delta 4), reused 20 (delta 3), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), done.
To https://github.com/ChayokSMedom/lab04
 * [new branch]      main -> main
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cd ~/workspace/projects/lab04
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cat > main.cpp << 'EOF'
#include <iostream>

int main() {
    std::cout << "Hello from CI!" << std::endl;
    return 0;
}
EOF
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cat > CMakeLists.txt << 'EOF' 
cmake_minimum_required(VERSION 3.10)
project(MyApp)

set(CMAKE_CXX_STANDARD 11)

add_executable(myapp main.cpp)

install(TARGETS myapp DESTINATION bin)
EOF
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ 
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cat > .github/workflows/ci.yml << 'EOF'
name: CI

on:
  push:
    branches: [ main, master ]
  pull_request:
    branches: [ main, master ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Configure
      run: cmake -H. -Bbuild -DCMAKE_INSTALL_PREFIX=_install
    
    - name: Build
      run: cmake --build build
    
    - name: Run tests (if any)
      run: |
        cd build
        ctest --output-on-failure || echo "No tests configured yet"
    
    - name: Install
      run: cmake --build build --target install
    
    - name: Run the app
      run: ./build/myapp
EOF
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git add main.cpp CMakeLists.txt .github/workflows/ci.yml
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git commit -m "Add simple app and improve CI workflow"
[main f37ff1a] Add simple app and improve CI workflow
 3 files changed, 19 insertions(+), 33 deletions(-)
 create mode 100644 main.cpp
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ git push origin main
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 2 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (7/7), 859 bytes | 429.00 KiB/s, done.
Total 7 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/ChayokSMedom/lab04
   cd774b4..f37ff1a  main -> main
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cd ~/workspace/reports/lab04
bash: cd: /home/reyne/workspace/reports/lab04: No such file or directory
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ mkdir -p ~/workspace/reports/lab04
reyne@reyne-VirtualBox:~/workspace/projects/lab04$ cd ~/workspace/reports/lab04
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ pwd
/home/reyne/workspace/reports/lab04
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ cd ~/workspace
git clone https://github.com/tp-labs/lab04 tasks/lab04
Cloning into 'tasks/lab04'...
remote: Enumerating objects: 84, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 84 (delta 0), reused 0 (delta 0), pack-reused 81 (from 1)
Receiving objects: 100% (84/84), 2.11 MiB | 2.24 MiB/s, done.
Resolving deltas: 100% (23/23), done.
reyne@reyne-VirtualBox:~/workspace$ cp tasks/lab04/README.md ~/workspace/reports/lab04/REPORT.md
reyne@reyne-VirtualBox:~/workspace$ cd ~/workspace/reports/lab04
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ ls -la ~/workspace/reports/lab04/REPORT.md
-rw-rw-r-- 1 reyne reyne 4239 May 18 11:13 /home/reyne/workspace/reports/lab04/REPORT.md
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ cat ~/workspace/reports/lab04/REPORT.md
## Laboratory work IV

Данная лабораторная работа посвещена изучению систем непрерывной интеграции на примере сервиса **Travis CI**

```sh
$ open https://travis-ci.org
```

## Tasks

- [ ] 1. Авторизоваться на сервисе **Travis CI** с использованием **GitHub** аккаунта
- [ ] 2. Создать публичный репозиторий с названием **lab04** на сервисе **GitHub**
- [ ] 3. Ознакомиться со ссылками учебного материала
- [ ] 4. Включить интеграцию сервиса **Travis CI** с созданным репозиторием
- [ ] 5. Получить токен для **Travis CLI** с правами **repo** и **user**
- [ ] 6. Получить фрагмент вставки значка сервиса **Travis CI** в формате **Markdown**
- [ ] 7. Выполнить инструкцию учебного материала
- [ ] 8. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```sh
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GITHUB_TOKEN=<полученный_токен>
```

```sh
$ cd ${GITHUB_USERNAME}/workspace
$ pushd .
$ source scripts/activate
```

```sh
$ \curl -sSL https://get.rvm.io | bash -s -- --ignore-dotfiles
$ echo "source $HOME/.rvm/scripts/rvm" >> scripts/activate
$ . scripts/activate
$ rvm autolibs disable
$ rvm install ruby-2.4.2
$ rvm use 2.4.2 --default
$ gem install travis
```

```sh
$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/lab04
$ cd projects/lab04
$ git remote remove origin
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab04
```

```sh
$ cat > .travis.yml <<EOF
language: cpp
EOF
```

```sh
$ cat >> .travis.yml <<EOF

script:
- cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
- cmake --build _build
- cmake --build _build --target install
EOF
```

```sh
$ cat >> .travis.yml <<EOF

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
EOF
```

```sh
$ travis login --github-token ${GITHUB_TOKEN}
```

```sh
$ travis lint
```

```sh
$ ex -sc '1i|<фрагмент_вставки_значка>' -cx README.md
```

```sh
$ git add .travis.yml
$ git add README.md
$ git commit -m"added CI"
$ git push origin master
```

```sh
$ travis lint
$ travis accounts
$ travis sync
$ travis repos
$ travis enable
$ travis whatsup
$ travis branches
$ travis history
$ travis show
```

## Report

```sh
$ popd
$ export LAB_NUMBER=04
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Homework

Вы продолжаете проходить стажировку в "Formatter Inc." (см [подробности](https://github.com/tp-labs/lab03#Homework)).

В прошлый раз ваше задание заключалось в настройке автоматизированной системы **CMake**.

Сейчас вам требуется настроить систему непрерывной интеграции для библиотек и приложений, с которыми вы работали в [прошлый раз](https://github.com/tp-labs/lab03#Homework). Настройте сборочные процедуры на различных платформах:
* используйте [TravisCI](https://travis-ci.com/) для сборки на операционной системе **Linux** с использованием компиляторов **gcc** и **clang**;
* используйте [AppVeyor](https://www.appveyor.com/) для сборки на операционной системе **Windows**.

## Links

- [Travis Client](https://github.com/travis-ci/travis.rb)
- [AppVeyour](https://www.appveyor.com/)
- [GitLab CI](https://about.gitlab.com/gitlab-ci/)

```
Copyright (c) 2015-2021 The ISC Authors
```
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ cat ~/workspace/reports/lab04/REPORT.md
## Laboratory work IV

Данная лабораторная работа посвещена изучению систем непрерывной интеграции на примере сервиса **Travis CI**

```sh
$ open https://travis-ci.org
```

## Tasks

- [ ] 1. Авторизоваться на сервисе **Travis CI** с использованием **GitHub** аккаунта
- [ ] 2. Создать публичный репозиторий с названием **lab04** на сервисе **GitHub**
- [ ] 3. Ознакомиться со ссылками учебного материала
- [ ] 4. Включить интеграцию сервиса **Travis CI** с созданным репозиторием
- [ ] 5. Получить токен для **Travis CLI** с правами **repo** и **user**
- [ ] 6. Получить фрагмент вставки значка сервиса **Travis CI** в формате **Markdown**
- [ ] 7. Выполнить инструкцию учебного материала
- [ ] 8. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```sh
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GITHUB_TOKEN=<полученный_токен>
```

```sh
$ cd ${GITHUB_USERNAME}/workspace
$ pushd .
$ source scripts/activate
```

```sh
$ \curl -sSL https://get.rvm.io | bash -s -- --ignore-dotfiles
$ echo "source $HOME/.rvm/scripts/rvm" >> scripts/activate
$ . scripts/activate
$ rvm autolibs disable
$ rvm install ruby-2.4.2
$ rvm use 2.4.2 --default
$ gem install travis
```

```sh
$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/lab04
$ cd projects/lab04
$ git remote remove origin
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab04
```

```sh
$ cat > .travis.yml <<EOF
language: cpp
EOF
```

```sh
$ cat >> .travis.yml <<EOF

script:
- cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
- cmake --build _build
- cmake --build _build --target install
EOF
```

```sh
$ cat >> .travis.yml <<EOF

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
EOF
```

```sh
$ travis login --github-token ${GITHUB_TOKEN}
```

```sh
$ travis lint
```

```sh
$ ex -sc '1i|<фрагмент_вставки_значка>' -cx README.md
```

```sh
$ git add .travis.yml
$ git add README.md
$ git commit -m"added CI"
$ git push origin master
```

```sh
$ travis lint
$ travis accounts
$ travis sync
$ travis repos
$ travis enable
$ travis whatsup
$ travis branches
$ travis history
$ travis show
```

## Report

```sh
$ popd
$ export LAB_NUMBER=04
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Homework

Вы продолжаете проходить стажировку в "Formatter Inc." (см [подробности](https://github.com/tp-labs/lab03#Homework)).

В прошлый раз ваше задание заключалось в настройке автоматизированной системы **CMake**.

Сейчас вам требуется настроить систему непрерывной интеграции для библиотек и приложений, с которыми вы работали в [прошлый раз](https://github.com/tp-labs/lab03#Homework). Настройте сборочные процедуры на различных платформах:
* используйте [TravisCI](https://travis-ci.com/) для сборки на операционной системе **Linux** с использованием компиляторов **gcc** и **clang**;
* используйте [AppVeyor](https://www.appveyor.com/) для сборки на операционной системе **Windows**.

## Links

- [Travis Client](https://github.com/travis-ci/travis.rb)
- [AppVeyour](https://www.appveyor.com/)
- [GitLab CI](https://about.gitlab.com/gitlab-ci/)

```
Copyright (c) 2015-2021 The ISC Authors
```
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ gist ~/workspace/reports/lab04/REPORT.md
gist: (WARNING) fread failed (command) on CGM file /home/reyne/workspace/reports/lab04/REPORT.md
gist: (WARNING) BEGIN METAFILE element missing
gist: (WARNING) /home/reyne/workspace/reports/lab04/REPORT.md is not a binary CGM, cannot open
gist> 
gist> cat ~/workspace/reports/lab04/REPORT.md | curl -X POST -H "Content-Type: application/json" -d '{"description":"Lab04 Report","public":true,"files":{"REPORT.md":{"content":"'$(cat ~/workspace/reports/lab04/REPORT.md | sed 's/"/\\"/g' | sed ':a;N;$!ba;s/\n/\\n/g')'"}}}' https://api.github.com/gists
gist: Unknown command: cat
      Type help for help.
gist> cat ~/workspace/reports/lab04/REPORT.md
gist: Unknown command: cat
      Type help for help.
gist> help
gist: Input Syntax:
     command [arg1] [arg2] ...
  Available commands are:  cgm, display, draw, eps, free, help, info, 
     open, ps, quit, send
  The quit command has two synonyms:  exit, end
  Any command except quit may be abbreviated by
  omitting characters from the right.
  The help command explains specific syntax, e.g.:
     help cgm
  describes the syntax of the cgm command.
  Five commands can be typed to a gist X window:
     nf   - forward n pages and draw (default 1)
     nb   - backward n pages and draw (default 1)
     ng   - go to page n and draw (default 1)
     s    - send current page
     q    - quit
gist> q
gist: The quit command cannot be abbreviated.
gist> quit
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ curl -s https://api.github.com/gists | head
[
  {
    "url": "https://api.github.com/gists/ab3da3da09eef0807d11d6561245b2a7",
    "forks_url": "https://api.github.com/gists/ab3da3da09eef0807d11d6561245b2a7/forks",
    "commits_url": "https://api.github.com/gists/ab3da3da09eef0807d11d6561245b2a7/commits",
    "id": "ab3da3da09eef0807d11d6561245b2a7",
    "node_id": "G_kwDOAOJ2EdoAIGFiM2RhM2RhMDllZWYwODA3ZDExZDY1NjEyNDViMmE3",
    "git_pull_url": "https://gist.github.com/ab3da3da09eef0807d11d6561245b2a7.git",
    "git_push_url": "https://gist.github.com/ab3da3da09eef0807d11d6561245b2a7.git",
    "html_url": "https://gist.github.com/Thyre/ab3da3da09eef0807d11d6561245b2a7",
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ gist ~/workspace/reports/lab04/REPORT.md
gist: (WARNING) fread failed (command) on CGM file /home/reyne/workspace/reports/lab04/REPORT.md
gist: (WARNING) BEGIN METAFILE element missing
gist: (WARNING) /home/reyne/workspace/reports/lab04/REPORT.md is not a binary CGM, cannot open
gist> quit
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ sudo apt remove gist
[sudo: authenticate] Password:             
Package 'gist' is not installed, so not removed
The following packages were automatically installed and are no longer required:
  linux-headers-7.0.0-14                   linux-modules-7.0.0-14-generic
  linux-headers-7.0.0-14-generic           linux-tools-7.0.0-14
  linux-image-unsigned-7.0.0-14-generic    linux-tools-7.0.0-14-generic
  linux-main-modules-zfs-7.0.0-14-generic
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 2
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ sudo apt install gist
The following packages were automatically installed and are no longer required:
  linux-headers-7.0.0-14                   linux-modules-7.0.0-14-generic
  linux-headers-7.0.0-14-generic           linux-tools-7.0.0-14
  linux-image-unsigned-7.0.0-14-generic    linux-tools-7.0.0-14-generic
  linux-main-modules-zfs-7.0.0-14-generic
Use 'sudo apt autoremove' to remove them.

Installing:
  gist

Installing dependencies:
  ruby-json

Summary:
  Upgrading: 0, Installing: 2, Removing: 0, Not Upgrading: 2
  Download size: 138 kB
  Space needed: 565 kB / 10.0 GB available

Continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu resolute/main amd64 ruby-json amd64 2.18.1+dfsg-1 [108 kB]
Get:2 http://archive.ubuntu.com/ubuntu resolute/universe amd64 gist all 6.0.0-3build1 [30.1 kB]
Fetched 138 kB in 1s (174 kB/s) 
Selecting previously unselected package ruby-json:amd64.
(Reading database… 224822 files and directories currently installed.)
Preparing to unpack …/ruby-json_2.18.1+dfsg-1_amd64.deb…
Unpacking ruby-json:amd64 (2.18.1+dfsg-1)…
Selecting previously unselected package gist.
Preparing to unpack …/gist_6.0.0-3build1_all.deb…
Unpacking gist (6.0.0-3build1)…
Setting up ruby-json:amd64 (2.18.1+dfsg-1)…
Setting up gist (6.0.0-3build1)…
Processing triggers for man-db (2.13.1-1build1)…
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ gist-paste ~/workspace/reports/lab04/REPORT.md
Error: Got Net::HTTPUnauthorized from gist: {
  "message": "Bad credentials",
  "documentation_url": "https://docs.github.com/rest",
  "status": "401"
}
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ gist ~/workspace/reports/lab04/REPORT.md
gist: (WARNING) fread failed (command) on CGM file /home/reyne/workspace/reports/lab04/REPORT.md
gist: (WARNING) BEGIN METAFILE element missing
gist: (WARNING) /home/reyne/workspace/reports/lab04/REPORT.md is not a binary CGM, cannot open
gist> quit
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ cat ~/workspace/reports/lab04/REPORT.md
## Laboratory work IV

Данная лабораторная работа посвещена изучению систем непрерывной интеграции на примере сервиса **Travis CI**

```sh
$ open https://travis-ci.org
```

## Tasks

- [ ] 1. Авторизоваться на сервисе **Travis CI** с использованием **GitHub** аккаунта
- [ ] 2. Создать публичный репозиторий с названием **lab04** на сервисе **GitHub**
- [ ] 3. Ознакомиться со ссылками учебного материала
- [ ] 4. Включить интеграцию сервиса **Travis CI** с созданным репозиторием
- [ ] 5. Получить токен для **Travis CLI** с правами **repo** и **user**
- [ ] 6. Получить фрагмент вставки значка сервиса **Travis CI** в формате **Markdown**
- [ ] 7. Выполнить инструкцию учебного материала
- [ ] 8. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```sh
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GITHUB_TOKEN=<полученный_токен>
```

```sh
$ cd ${GITHUB_USERNAME}/workspace
$ pushd .
$ source scripts/activate
```

```sh
$ \curl -sSL https://get.rvm.io | bash -s -- --ignore-dotfiles
$ echo "source $HOME/.rvm/scripts/rvm" >> scripts/activate
$ . scripts/activate
$ rvm autolibs disable
$ rvm install ruby-2.4.2
$ rvm use 2.4.2 --default
$ gem install travis
```

```sh
$ git clone https://github.com/${GITHUB_USERNAME}/lab03 projects/lab04
$ cd projects/lab04
$ git remote remove origin
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab04
```

```sh
$ cat > .travis.yml <<EOF
language: cpp
EOF
```

```sh
$ cat >> .travis.yml <<EOF

script:
- cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
- cmake --build _build
- cmake --build _build --target install
EOF
```

```sh
$ cat >> .travis.yml <<EOF

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
EOF
```

```sh
$ travis login --github-token ${GITHUB_TOKEN}
```

```sh
$ travis lint
```

```sh
$ ex -sc '1i|<фрагмент_вставки_значка>' -cx README.md
```

```sh
$ git add .travis.yml
$ git add README.md
$ git commit -m"added CI"
$ git push origin master
```

```sh
$ travis lint
$ travis accounts
$ travis sync
$ travis repos
$ travis enable
$ travis whatsup
$ travis branches
$ travis history
$ travis show
```

## Report

```sh
$ popd
$ export LAB_NUMBER=04
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Homework

Вы продолжаете проходить стажировку в "Formatter Inc." (см [подробности](https://github.com/tp-labs/lab03#Homework)).

В прошлый раз ваше задание заключалось в настройке автоматизированной системы **CMake**.

Сейчас вам требуется настроить систему непрерывной интеграции для библиотек и приложений, с которыми вы работали в [прошлый раз](https://github.com/tp-labs/lab03#Homework). Настройте сборочные процедуры на различных платформах:
* используйте [TravisCI](https://travis-ci.com/) для сборки на операционной системе **Linux** с использованием компиляторов **gcc** и **clang**;
* используйте [AppVeyor](https://www.appveyor.com/) для сборки на операционной системе **Windows**.

## Links

- [Travis Client](https://github.com/travis-ci/travis.rb)
- [AppVeyour](https://www.appveyor.com/)
- [GitLab CI](https://about.gitlab.com/gitlab-ci/)

```
Copyright (c) 2015-2021 The ISC Authors
```
reyne@reyne-VirtualBox:~/workspace/reports/lab04$ 
