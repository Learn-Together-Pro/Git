# Cheat sheets

### rebase

```shell
git rebase master
git rebase master feature1

# attach current branch( feature1 ) after master moving branch pointer
# Before                              After
# A---B---C---F---G (master)          A---B---C---F---G (master)
#          \                                           \
#           D---E (HEAD feature1)                   D'---E' (HEAD feature1)
```

### rebase selective moving branch pointer

```shell
git rebase --onto F D

# attach to F what godes after D
# Before                                    After
# A---B---C---F---G (branch)                A---B---C---F---G (branch)
#          \                                             \
#           D---E---H---I (HEAD my-branch)                E'---H'---I' (HEAD my-branch)
```

### rebase selective without moving branch pointer

```shell
git rebase --onto F D H
git rebase --onto F D HEAD

# rebase selective to F what goes after D stopping at H
# Before                                    After
# A---B---C---F---G (branch)                A---B---C---F---G (branch)
#          \                                        |    \
#           D---E---H---I (HEAD my-branch)          |     E'---H' (HEAD)
#                                                    \
#                                                     D---E---H---I (my-branch)
```

### commits drop

```shell
git rebase --onto B D
git rebase --onto B D branch1

# attach to B what goes after D moving branch pointer
# Before                                 After
# A---B---C---D---E---F (HEAD branch)    A---B---E'---F' (HEAD branch)
```

### git areas

![cheatsheet](./asset/cheatsheet.jpg)
