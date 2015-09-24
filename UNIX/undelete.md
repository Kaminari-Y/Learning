some times you delete files not on purpose.
mkdir a trash for my ENV

mkdir ~/.trash

vim .bashrc or .bash_profile

to_trash(){
  for file in $@
  do
    mv $file ~/.trash
  done
  }
alias rm='to_trash'


then, when you use "rm XXX", the XXX will move to ~/.trash.
because the file doesn't delete from PC, so you have to clean the trash

/bin/rm -rf ~/.trash
or
make a same file name to override the file you want to delete for sure.
