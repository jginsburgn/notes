# Reset the Author Info (And Possible Else) Of Whole Branch

1. Do an interactive rebase of the target branch on itself:

    ```
    git rebase --interactive --root
    ```

1. Set `edit` actions on all to-rebase commits.
1. Repeatedly `amend` commits and `continue` rebase actions, until rebase ends:

    ```
    git commit --amend --date="$(git show -s --format=%ci REBASE_HEAD)" --reset-author --no-edit
    git rebase --continue
    ```

###### March 13, 2019 Jonathan Ginsburg