# SFDX Sample "Project 1" For CumulusCI Task Test

## Summary
This is an SFDX sample repository for CumulusCI (CCI) task test.
This repository is supoosed to be used with 
[another repository](https://github.com/TamiTakamiya/sfdx-proj2).

## Setup
1. Clone this repository on your PC
1. Set your Dev Hub org with
    ```
    sfdx auth:web:login -d -a DevHub 
    ```
## Instructions
Try to execute two tasks defined in another repository.
The `cumulusci.yml` contained in this repo has a source
definition to the another repository and theoretically
those tasks can be executed without problems.
```
sources:
    sfdx-proj2:
        github: https://github.com/TamiTakamiya/sfdx-proj2
        branch: main
```

1. dxtask
    ```
    cci task run sfdx-proj2:dxtask
    ```
    This task should display the output of `sfdx force:org:list` command.

2. mytask
    ```
    cci task run sfdx-proj2:mytask
    ```
    This task is supposed to invoke the `MyTask` class defined 
    in `scripts/tasks/MyTask.py`in another repository
    and print the output message `This is my task.` 

    However, it fails with the following message:
    ```
    No module named 'scripts.tasks'
    ```