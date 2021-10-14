# rename
Rename files with Perl power

# Rename files with regular expressions

For example, to rename all files matching *.bak to strip the extension, you might say:

```sh
rename 's/\.bak$//' *.bak
```

But you're not limited to simple substitutions - you have at your disposal the full expressive power of Perl. To add those extensions back on, for instance, say this:

```
rename '$_ .= ".bak"' *
```

or even:
```
rename 's/$/.bak/' *
```

To translate uppercase names to lowercase, you'd use:
```
rename 'tr/A-Z/a-z/' *
```

And how about these?

```
rename 's/foo/bar/; $_ = $was if -e' *foo*
```

```
find . -print | rename 's/readme/README/i'
```

```
find . -print | rename 's/$/.old/ if -M $_ > 0.5'
```
