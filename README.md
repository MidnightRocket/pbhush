# Source code available at [Codeberg](https://codeberg.org/MidnightRocket/pbhush/)

In the spirit of [#GiveUpGithub](https://giveupgithub.org/) the source code for this
project can be found on [Codeberg](https://codeberg.org/MidnightRocket/pbhush/),
a Github alternative driven by a non profit organization based in the EU!

This repository merely exists to allow you to discover this project on Github.

# pbhush

This is a small cli utility which copies text from `STDIN` to the clipboard,
whilst marking the content as secret. This means conforming clipboard managers,
knows that they should not save the content in their history.
This includes the new clipboard history feature in [MacOS Tahoe](https://support.apple.com/guide/mac-help/search-your-clipboard-history-mchl40d5b86b/mac)\*.

\**Despite not officially documented, this is the behavior I am observing.*

## Install

### From source

Clone the git repository:

```sh
git clone "https://codeberg.org/MidnightRocket/pbhush.git"

cd "pbhush"
```

Use make to install for current user only `$HOME/.local/bin`:

```sh
make install-local
```

**Or** system wide (`/usr/local/bin`). This will prompt for password:

```sh
make install
```

## Usage

Simply pipe secret data into the `pbhush` utility:

```sh
echo some secret | pbhush
```

It is also possible to automatically clear the clipboard
after `N` seconds using:

```sh
echo some secret | pbhush --ttl 30
```

By default will copied content not synchronize to iCloud devices via
[Universal Clipboard](https://support.apple.com/en-us/102430).
To allow syncing content use:

```sh
echo some secret | pbhush --alow-sync
```

For more help use:

```sh
pbhush --help
```

## Attribution

- This project is very much inspired by [github.com/roosto/pbhush](https://github.com/roosto/pbhush).
- `pbhush` marks content with `org.nspasteboard.ConcealedType`
  defined at [nspasteboard.org](https://nspasteboard.org/)

### Dependencies

- [github.com/apple/swift-argument-parser](https://github.com/apple/swift-argument-parser/)
