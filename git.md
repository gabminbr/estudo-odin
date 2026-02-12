## using branches
- fazer novas branches:
```bash
git branch <nova_branch>
```
- mudar para a branch:
```bash
git checkout <nome_branch>
```
- juntando as duas, criando e ja alterando para a nova branch criada:
```bash
git checkout -b <nova_branch>
```
- para ver todas as branches:
```bash
git branch
```
- após fazer as alterações que queria na branch, tem que mergear pra main, mas para usar esse comando, voce vai ter que estar na branch que vai receber as mudancas da branch, exemplo, voce esta na main e quer trazer as mudancas feitas na branch teste
```bash
git merge teste
```
- deletar a branch (se já tiver mergeado para a main):
```bash
git branch -d <branch_name>
```
- deletar (sem ter mergeado):
```bash
git branch -D <branch_name>
```
