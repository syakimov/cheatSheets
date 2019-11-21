DB Migration -> add new table
1. Create a file for the migration

* Rebase structure sql -> you should not amend this file

```
git pull -r origin master
git co db/structure.sql --theirs
bundle exec rails db:migrate
git add db/structure.sql
git rebase --continue
# git push -f

```

rake routs | grep {path_to_controller} => easy way to make http requests


Make changes to a migration which is not the last one:

```
# rollback only this specific migration
bundle exec rails db:migrate:down VERSION=20191023103012
bundle exec rails db:migrate
```
