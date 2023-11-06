# How to ...

### ... make a symlink private_html to public_html.
```console
# remove private_html dir
rm -r private_html

# make symlink
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

### ... fetch and display Laravel validation errors
snippet from Kemeling.nl
```javascript
this.errorMessages = [];

fetch('/api/registrants/store', {
    method: 'POST',
    headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json',
        'X-CSRF-TOKEN': this.$refs.token.value
    },
    body: JSON.stringify(this.form)
})
.then(function(response) {
    if (response.ok) {
        return response.json();
    }

    return Promise.reject(response);
})
.then(json => {
    this.form.ref = json.ref
    this.step++;
})
.catch(response => {
    response.json().then((json) => {
        for (const [key, values] of Object.entries(json.errors)) {
            this.errorMessages.push(values[0])
        }
    })
})
```
