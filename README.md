# remove-sensitive-data-test

## Reference:
https://help.github.com/articles/removing-sensitive-data-from-a-repository/
https://rtyley.github.io/bfg-repo-cleaner/

## Mirror Your Branch And Take Backup:

$ git clone --mirror git://example.com/some-big-repo.git

Download BFG Repo Cleaner Java Jar file from here: https://github.com/shadman/openssl-fips-module-build

After downloading above jar file you may use bfg.jar file like this:

> $ bfg --delete-files <fileName.extension> <git repo name>.git


Place that bfg.jar file in your repo.

We are assuming test.php file is the file which we are going to remove from repository and history

> $ java -jar bfg.jar --delete-files test.php remove-sensitive-data-test.git

> $ cd remove-sensitive-data-test.git

> $ git reflog expire --expire=now --all && git gc --prune=now --aggressive

> $ git push

Will be removed from all branches except master, as you are in mirror directory

Go to your branch directory and switch to master branch

> $ git pull origin

And you are done.

Cheers !
