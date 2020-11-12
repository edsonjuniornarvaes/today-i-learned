# Map the branch.

#### Verifique a existência de mapeamento da branch, o seguinte aviso irá aparecer caso o mapeamento não exista.

> There is no tracking information for the current branch.
> Please specify which branch you want to merge with.
> See git-pull(1) for details.

>   git pull <remote> <branch>

>   If you wish to set tracking information for this branch you can do so with:

>   git branch --set-upstream-to=origin/<branch> develop

### Faça o checkout na branch em que deseja criar o mapeamento.

```bash 
$ git checkout branchname
```

### Diga para o upstream qual branch está mapeando.
```bash 
git branch --set-upstream-to=origin/branchname branchname
```

> A partir de agora, ao invés de sempre informar a origem como por exemplo: git pull origin master, você irá apenas solicitar: git pull, pois a branch já está mapeada