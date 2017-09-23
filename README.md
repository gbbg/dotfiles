# Dot Files
## 2017-09-23 strap’d with commit `9f4d448` and `0a3bf5c`

### Not Fully Automated
These items below were done manually:
- join single machine to an isolated guest network behind NAT for a little better security.  Note freshly installed OSX was not yet updated before running this script
- update `STRAP_GITHUB_USER` value in strap.sh
- sign into app store, this should be done before installing / running `mas` brew
- secrets, such as git email address, ssh private keys
- adding more input sources such as keyboards for other languages
- disable keyboard text auto correct settings
- accessibility settings
- configure dock position on screen
- non-public files such as ssh keys, and `git config --global user.email "you@example.com"`

### Stats
* Fresh install macOS Sierra 10.12.6
* Macbook Pro Retina A1502 Early 2015
* Before: 10.09GB used (as shown in Disk Utility, this was right after fresh OS X install)
* After: 20.2GB used

### Time taken
`bin/strap.sh` (from `strap` repo) took this long:

- first run took approx 11 minutes, but Brewfile failed:
```
pros-MBP:strap p$ time bash bin/strap.sh
. . .
real	11m32.247s
user	0m24.216s
sys	0m10.783s
```
Above timing excludes Brewfile, which errored out. `linksapps` is not understood within Brewfile:
```
Error: Invalid Brewfile: undefined local variable or method `linkapps' for #<Bundle::Dsl:0x007ffe96bd2b20>
```

- second run took approx 60 minutes, with updated Brewfile at commit `0a3bf5c`. mas Xcode was main reason why it took this long.  Xcode download took a long time


## Installation
Customise the contents of [`gitconfig-user`](https://github.com/MikeMcQuaid/dotfiles/blob/master/gitconfig-user).
This is used for user-specific customisations of every other file.

Run [`script/setup`](https://github.com/MikeMcQuaid/dotfiles/blob/master/script/setup)
after checkout to symlink (or copy) everything in this directory to your home directory.

## License
These dot files are licensed under the [GPLv3 License](https://en.wikipedia.org/wiki/GNU_General_Public_License).
The full license text is available in [LICENSE.txt](https://github.com/MikeMcQuaid/dotfiles/blob/master/LICENSE.txt).
