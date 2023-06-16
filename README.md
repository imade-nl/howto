# How to ...

### ... make a symlink private_html to public_html.
```console
// remove private_html dir
rm -r private_html

// make symlink
ln -s public_html private_html
```

### ... delete a git tag locally and remote
```console
# delete local tag '12345'
git tag -d 12345
# delete remote tag '12345' (eg, GitHub version too)
git push origin :refs/tags/12345
# alternative approach
git push --delete origin tagName
git tag -d tagName
```
