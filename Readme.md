Init Commit

mkdir trip

cd trip

git remote -v

git remote rm origin

git remote add origin https://github.com/fidelisfelipe/trip.git

git init

git config --global user.name "My Name"

git config --global user.email my@example.com

git commit -m"init commit"

git config --global push.default simple

git push --set-upstream origin master

__________________________________________________
Re-author-rewrite

git filter-branch --env-filter '

OLD_EMAIL="unknown"
CORRECT_NAME="Fidelis"
CORRECT_EMAIL="atosfiel@gmail.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
___________________________________________________
