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


