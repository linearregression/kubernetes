# Devnotes

* Prep your fork for go project so your go import contains your checkins
* git clone git@github.com:kubernetes/kubernetes.git
Fork the k8 repo to personal
* git remote add fork MYFORK
[Optional]
Just to keep the workflow consistent with other languages
* git remote rename origin upstream 
* git remote rename fork origin
[Checkout]
Assuming your keep origin and fork as is with no remote rename:
* git checkout -b fix-stuff
* git commit -m "some comment"
* git push fork fix-stuff
Reset master 
git fetch origin
git reset--hard origin/master

