# Varbase Sub Profile Generator

We do have a generator for new Varbase sub profiles, which could help you in a quick way.

**For Example:** If we want to create a new Varbase sub profile named **cv** , we could do the following you could run the following commands in your local terminal.


```
mkdir /var/www/html/products

cd /var/www/html/products

git clone git@bitbucket.org:Vardot/varbase-subprofile-generator.git

cd /var/www/html/products/varbase-subprofile-generator

git checkout 8.4.08

bash create-new-varbase-subprofile.sh "cv" -vvv
```

After that you will have a new **cv** sub p**rofile cv-project** as you can see in the following:


```
cd /var/www/html/products/varbase-subprofile-generator

ll

create-new-varbase-subprofile.sh

cv/
cv-project/

.git/
README.md
settings.yml

varbase_subprofile_basic/
varbase-subprofile-basic-project/
```

You could download the latest generator for latest Varbase from https://bitbucket.org/Vardot/varbase-subprofile-generator/downloads/?tab=tags


