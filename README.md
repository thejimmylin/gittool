# gitext

## gitext's `use` (`git use`)

Control Git config, SSH keys, and commit signing keys for multiple Git profiles.

https://github.com/user-attachments/assets/9fc20bea-6a79-426e-8858-085109a729f5

### How to use `use`

You may run it using `pipx`, but usually you want to set it as a `git` alias

```sh
...
[alias]
	use = npx gitext@1.0.11 use
...
```

You then run it with `git use`

```sh
# Create a new profile, including a new SSH key
> git use b00502013@gmail.com 'Jimmy Lin'
Created profile Jimmy Lin <b005020132@gmail.com>

# Create another profile
> git use contact@jimmylin.org 'Jimmy'
Created profile Jimmy <contact@jimmylin.org>

# Use it
> git use b00502013@gmail.com
Jimmy Lin <b005020132@gmail.com>

# Fuzzy matching is supported (only when purely activating a profile, not deleting or updating)
> git use cont
Jimmy <contact@jimmylin.org>

# List all profiles
> git use
* Jimmy <contact@jimmylin.org>
Created profile Jimmy Lin <b005020132@gmail.com>

# Delete a profile
> git use b00502013@gmail.com -d
Deleted profile Jimmy Lin <b005020132@gmail.com>

# Update profile name (`git`'s `user.name`)
> git use b00502013@gmail.com 'JL' -u
Updated profile as JL <b00502013@gmail.com>
```

# Known issues

- `-u`, `-d` can only be placed at the end of the command
