# Отчёт:

```
reyne@reyne-VirtualBox:~/reyne/workspace$ export GITHUB_USERNAME=reyne
reyne@reyne-VirtualBox:~/reyne/workspace$ cd ${GITHUB_USERNAME}/workspace
bash: cd: reyne/workspace: No such file or directory
reyne@reyne-VirtualBox:~/reyne/workspace$ reyne@reyne-VirtualBox:~/reyne/workspace$ export GITHUB_USERNAME=reyne
reyne@reyne-VirtualBox:~/reyne/work
bash: reyne@reyne-VirtualBox:~/reyne/workspace$: No such file or directory
bash: reyne@reyne-VirtualBox:~/reyne/work: No such file or directory
reyne@reyne-VirtualBox:~/reyne/workspace$ ls -la projects/
total 20
drwxrwxr-x 5 reyne reyne 4096 May 18 01:02 .
drwxrwxr-x 8 reyne reyne 4096 May 18 01:07 ..
drwxrwxr-x 6 reyne reyne 4096 May 17 23:45 lab02
drwxrwxr-x 6 reyne reyne 4096 May 18 00:52 lab03
drwxrwxr-x 8 reyne reyne 4096 May 18 00:48 lab03_old
reyne@reyne-VirtualBox:~/reyne/workspace$ rm -rf projects/lab03
reyne@reyne-VirtualBox:~/reyne/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab02.git projects/lab03
Cloning into 'projects/lab03'...
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/reyne/lab02.git/'
reyne@reyne-VirtualBox:~/reyne/workspace$ git config --global credential.helper ""
reyne@reyne-VirtualBox:~/reyne/workspace$ git clone https://github.com/${GITHUB_USERNAME}/lab02.git projects/lab03
Cloning into 'projects/lab03'...
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/reyne/lab02.git/'
reyne@reyne-VirtualBox:~/reyne/workspace$ git clone https://ChayokSMedom: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@github.com/ChayokSMedom/lab02.git projects/lab03
Cloning into 'projects/lab03'...
remote: Enumerating objects: 15, done.
remote: Counting objects: 100% (15/15), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 15 (delta 1), reused 11 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (15/15), 4.55 KiB | 4.55 MiB/s, done.
Resolving deltas: 100% (1/1), done.
reyne@reyne-VirtualBox:~/reyne/workspace$ cd projects/lab03
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git remote remove origin
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ export GITHUB_USERNAME=ChayokSMedom
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$  git remote add origin https://github.com/${GITHUB_USERNAME}/lab03.git
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ls print.o
print.o
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nm print.o | grep print
0000000000000000 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
000000000000002a T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ar rvs print.a print.o
ar: creating print.a
a - print.o
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ file print.a
print.a: current ar archive
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ g++ -std=c++11 -I./include -c examples/example1.cpp
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ls example1.o
example1.o
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ g++ example1.o print.a -o example1
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ./example1 && echo
hello
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ g++ -std=c++11 -I./include -c examples/example2.cpp
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nm example2.o
0000000000000000 V DW.ref.__gxx_personality_v0
                 U __gxx_personality_v0
0000000000000000 T main
                 U memcpy
                 U __stack_chk_fail
                 U strlen
                 U _Unwind_Resume
                 U _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
                 U _ZdlPv
0000000000000000 W _ZNKSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE11_M_is_localEv
0000000000000000 W _ZNKSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE13_M_local_dataEv
0000000000000000 W _ZNKSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE16_M_get_allocatorEv
0000000000000000 W _ZNKSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE7_M_dataEv
0000000000000000 W _ZNKSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE8max_sizeEv
0000000000000000 W _ZNSt11char_traitsIcE4copyEPcPKcm
0000000000000000 W _ZNSt11char_traitsIcE6assignERcRKc
0000000000000000 W _ZNSt11char_traitsIcE6lengthEPKc
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEEC1EPKcSt13_Ios_Openmode
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcE10deallocateEPcm
0000000000000000 W _ZNSt15__new_allocatorIcE8allocateEmPKv
0000000000000000 W _ZNSt15__new_allocatorIcED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcED2Ev
0000000000000000 n _ZNSt15__new_allocatorIcED5Ev
0000000000000000 W _ZNSt19__ptr_traits_ptr_toIPccLb0EE10pointer_toERc
0000000000000000 W _ZNSt19__ptr_traits_ptr_toIPKcS0_Lb0EE10pointer_toERS0_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE10_M_destroyEm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE10_M_disposeEv
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE11_M_capacityEm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE11_S_allocateERS3_m
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderC1EPcRKS3_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderC2EPcRKS3_
0000000000000000 n _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderC5EPcRKS3_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderD1Ev
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderD2Ev
0000000000000000 n _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_Alloc_hiderD5Ev
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tag
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE13_M_local_dataEv
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE13_M_set_lengthEm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE13_S_copy_charsIPKcEEvPcT_S9_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE16_M_get_allocatorEv
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE7_M_dataEPc
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE7_S_copyEPcPKcm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE9_M_createERmm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE9_M_lengthEm
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC1EPKcRKS3_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC2EPKcRKS3_
0000000000000000 n _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC5EPKcRKS3_
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED1Ev
0000000000000000 W _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED2Ev
0000000000000000 n _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED5Ev
                 U _Znwm
                 U _ZSt17__throw_bad_allocv
                 U _ZSt19__throw_logic_errorPKc
                 U _ZSt20__throw_length_errorPKc
                 U _ZSt21ios_base_library_initv
0000000000000000 W _ZSt3minImERKT_S2_S2_
0000000000000001 r _ZStL19piecewise_construct
0000000000000000 r _ZStL6ignore
0000000000000000 W _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardC1EPS4_
0000000000000000 W _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardC2EPS4_
0000000000000000 n _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardC5EPS4_
0000000000000000 W _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardD1Ev
0000000000000000 W _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardD2Ev
0000000000000000 n _ZZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEE12_M_constructIPKcEEvT_S8_St20forward_iterator_tagEN6_GuardD5Ev
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ g++ example2.o print.a -o example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ./example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat log.txt && echo
hello
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf example1.o example2.o print.o
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf print.a
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf example1 example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf log.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(print)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
add_library(print STATIC \${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake -H. -B_build
CMake Error at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 has been removed from CMake.

  Update the VERSION argument <min> value.  Or, use the <min>...<max> syntax
  to tell CMake that the project requires at least <min> but has been updated
  to work with policies introduced by <max> or earlier.

  Or, add -DCMAKE_POLICY_VERSION_MINIMUM=3.5 to try configuring anyway.


-- Configuring incomplete, errors occurred!
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --version
cmake version 4.2.3

CMake suite maintained and supported by Kitware (kitware.com/cmake).
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano CMakeLists.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake -H. -B_build
-- The C compiler identification is GNU 15.2.0
-- The CXX compiler identification is GNU 15.2.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (1.2s)
-- Generating done (0.0s)
-- Build files have been written to: /home/reyne/reyne/workspace/projects/lab03/_build
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat >> CMakeLists.txt <<EOF

target_link_libraries(example1 print)
target_link_libraries(example2 print)
EOF
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/reyne/reyne/workspace/projects/lab03/_build
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/example1.dir/examples/example1.cpp.o
[ 66%] Linking CXX executable example1
[ 66%] Built target example1
[ 83%] Building CXX object CMakeFiles/example2.dir/examples/example2.cpp.o
[100%] Linking CXX executable example2
[100%] Built target example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build --target print
[100%] Built target print
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build --target example1
[ 50%] Built target print
[100%] Built target example1
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build --target example2
[ 50%] Built target print
[100%] Built target example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ ls -la _build/libprint.a
-rw-rw-r-- 1 reyne reyne 2270 May 18 01:27 _build/libprint.a
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ _build/example1 && echo
hello
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat log.txt && echo
cat: log.txt: No such file or directory
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ _build/example2
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat log.txt && echo
hello
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf log.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git clone https://github.com/tp-labs/lab03 tmp
Cloning into 'tmp'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61 (from 1)
Receiving objects: 100% (91/91), 1.02 MiB | 3.69 MiB/s, done.
Resolving deltas: 100% (41/41), done.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ mv -f tmp/CMakeLists.txt .
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ rm -rf tmp
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cat CMakeLists.txt
cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(BUILD_EXAMPLES "Build examples" OFF)

project(print)

add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

target_include_directories(print PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
CMake Error at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 has been removed from CMake.

  Update the VERSION argument <min> value.  Or, use the <min>...<max> syntax
  to tell CMake that the project requires at least <min> but has been updated
  to work with policies introduced by <max> or earlier.

  Or, add -DCMAKE_POLICY_VERSION_MINIMUM=3.5 to try configuring anyway.


-- Configuring incomplete, errors occurred!
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano CMakeLists.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/reyne/reyne/workspace/projects/lab03/_build
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ cmake --build _build --target install
[100%] Built target print
Install the project...
-- Install configuration: ""
-- Installing: /home/reyne/reyne/workspace/projects/lab03/_install/lib/libprint.a
-- Installing: /home/reyne/reyne/workspace/projects/lab03/_install/include
-- Installing: /home/reyne/reyne/workspace/projects/lab03/_install/include/print.hpp
-- Installing: /home/reyne/reyne/workspace/projects/lab03/_install/cmake/print-config.cmake
-- Installing: /home/reyne/reyne/workspace/projects/lab03/_install/cmake/print-config-noconfig.cmake
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ tree _install
_install
├── cmake
│   ├── print-config.cmake
│   └── print-config-noconfig.cmake
├── include
│   └── print.hpp
└── lib
    └── libprint.a

4 directories, 4 files
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git add CMakeLists.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git commit -m"added CMakeLists.txt"
[main 77f4442] added CMakeLists.txt
 1 file changed, 36 insertions(+)
 create mode 100644 CMakeLists.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push origin main
Username for 'https://github.com': ChayokSMedom
Password for 'https://ChayokSMedom@github.com': 
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/ChayokSMedom/lab03.git/'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git remote set-url origin https://ChayokSMedom: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@github.com/ChayokSMedom/lab03.git
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push origin main
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/ChayokSMedom/lab03.git/'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git remote add origin https://ChayokSMedom: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@github.com/ChayokSMedom/lab03.git
error: remote origin already exists.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git remote set-url origin https://ChayokSMedom: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@github.com/ChayokSMedom/lab03.git
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push origin main
To https://github.com/ChayokSMedom/lab03.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab03.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push -f origin main
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 2 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (18/18), 5.23 KiB | 1.74 MiB/s, done.
Total 18 (delta 2), reused 14 (delta 1), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
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
remote:          - commit: 88e3237f4ab62f491ff16994dc5b1786ffabeadb
remote:            path: README.md:46
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab03/security/secret-scanning/unblock-secret/3DrwuGT5PcdKYq3wl4cQBH3U7OT
remote:     
remote: 
remote: 
To https://github.com/ChayokSMedom/lab03.git
 ! [remote rejected] main -> main (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab03.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push -f origin mai
error: src refspec mai does not match any
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab03.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push -f origin main
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 2 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (18/18), 5.23 KiB | 5.23 MiB/s, done.
Total 18 (delta 2), reused 14 (delta 1), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
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
remote:          - commit: 88e3237f4ab62f491ff16994dc5b1786ffabeadb
remote:            path: README.md:46
remote:     
remote:        (?) To push, remove secret from commit(s) or follow this URL to allow the secret.
remote:        https://github.com/ChayokSMedom/lab03/security/secret-scanning/unblock-secret/3DrwuGT5PcdKYq3wl4cQBH3U7OT
remote:     
remote: 
remote: 
To https://github.com/ChayokSMedom/lab03.git
 ! [remote rejected] main -> main (push declined due to repository rule violations)
error: failed to push some refs to 'https://github.com/ChayokSMedom/lab03.git'
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git add README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git commit --amend --no-edit
[main a12ccaf] added CMakeLists.txt
 Date: Mon May 18 01:31:49 2026 +0300
 2 files changed, 37 insertions(+), 1 deletion(-)
 create mode 100644 CMakeLists.txt
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git show | grep -i "ghp_"
-reyne@reyne-VirtualBox:~/reyne/workspace$ git remote add origin https://ChayokSMedom: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@github.com/ChayokSMedom/lab02.git
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git log --oneline -5
a12ccaf (HEAD -> main) added CMakeLists.txt
88e3237 Create README.md
e4f88af added sources
a8b7272 Add .gitignore
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git rebase -i HEAD~3
Stopped at 88e3237...  # Create README.md
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git add README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git rebase --continue
[detached HEAD 5d80197] Create README.md
 Author: helpme <123084286+ChayokSMedom@users.noreply.github.com>
 Date: Sun May 17 23:56:28 2026 +0300
 1 file changed, 212 insertions(+)
 create mode 100644 README.md
Successfully rebased and updated refs/heads/main.
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ nano README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ y
y: command not found
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git add README.md
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git rebase --continue
fatal: no rebase in progress
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ git push -f origin main
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 2 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (18/18), 4.59 KiB | 1.53 MiB/s, done.
Total 18 (delta 2), reused 11 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/ChayokSMedom/lab03.git
 + b8b8b60...3ffa3fc main -> main (forced update)
reyne@reyne-VirtualBox:~/reyne/workspace/projects/lab03$ 

```
