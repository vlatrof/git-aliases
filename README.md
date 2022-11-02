# git-aliases
Git aliases that i use. If you want to use it put this section in your .gitconfig file

    [alias]
        
        # git status
        s = status
        
        # get branches info
        b = branch -a
        
        # draw graph of commits in different ways
        # (lg1, lg2, lg3) or lg that equals lg1
        lg = lg1
        lg1 = lg1-specific --all
        lg2 = lg2-specific --all
        lg3 = lg3-specific --all
        lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'
        lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(auto)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
        lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(auto)%d%C(reset)%n''          %C(white)%s%C(reset)%n''          %C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)'

    
        # chain of commands:
        # 1. index all changes
        # 2. create new commit with provided message
        # 3. push this current branch to upstream branch
        # example of using:
        # > git acp "test commit message"
        acp = "!f() { git add . && git commit -m\""$@"\" && git push; }; f"
