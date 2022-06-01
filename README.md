# golang-united-school-homework-7

The goal of this homework is to write tests in `students_test.go` file and achieve as much coverage as possible.

Inside this repo you can find 2 files and one directory:
1. File `toBeTested.go` contains functions which should be tested. Do not change this file.
2. File `students_test.go` is a boilerplate of file with your tests. At the start of this file you can find `init()` function, which is required because of peculiarities of Autocode platform. This function will copy your file to `/autocode` folder, do not touch this function.
3. Folder `/autocode` to which your test will be automatically copied when you locally trigger your tests.

Workflow to pass a homework: 
1. Write tests in `students_test.go`
2. Run your tests locally to check it status and resulted coverage. Each time you run tests your code will be copied to `/autocode` folder (NOTE: the name of this file is `students_test` - it's correct).
3. Repeat steps 1 and 2 before you get desired result.
4. When you will be ready to submit and test you solution on Autocode, you will need to commit and push `autocode/students_test` file to git. **Make sure that this file was automatically updated.** 

After submitting of your solution on Autocode you will get some logs. If you faced with some error or did not achieve full coverage - modify your code and try again.

Prerequisite:
- Execute commands
    - `go mod init`
    - `go mod tidy`