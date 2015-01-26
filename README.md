# rimrafall

This is to show that `npm install` can be as dangerous as `curl dangerous.com | sh`.

### update, it's off the npm registry

It was [taken off the npm registry](https://twitter.com/othiym23/status/559759478774439936) but it solves nothing really, anyone could make malicious modules like this and mask it as a useful module that has a desired use case. Let's try to find ways to **really** make npm safe ;)

### update 2, no intent of being malicious

No, I did not name this package `rimrafall`, submited it to [HN](https://news.ycombinator.com/item?id=8947493), clearly stated what it does and clearly told people **not to install** it with the purpose of having people delete stuff on their computers.

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
