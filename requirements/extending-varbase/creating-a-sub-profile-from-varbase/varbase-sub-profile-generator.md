# Varbase Sub Profile Generator

We do have generator for new Varbase sub profiles
as you could run the following commands in your local terminal.

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



