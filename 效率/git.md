### .gitignore
~/.gitignore + folder/.gitignore

### TODO: alias
alias reignore='git rm -r --cached . && git add .'
alias whyignore='git check-ignore -v'
alias gg='git lg'
[alias]
    lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%ci) %C(bold blue) <%an>%Creset' --abbrev-commit


### 常用命令
///TODO：
gg file_name
git branch -a
git branch --remote

### Merge rebase
过多的 merge 容易导致时间线保证，影响阅读。
rebase 更清晰优雅，但是破坏了真实的提交记录。