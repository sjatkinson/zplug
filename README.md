# zplug: Zplug is a minimal `zsh` plugin manager

## Prerequisites

- [ZSH](https://www.zsh.org/)
- a nerd font (optional)

To get your nerd font check out [getNF](https://github.com/ronniedroid/getnf) project or visit [NerdFonts](https://www.nerdfonts.com/) site.

## Install

TBD


**Zplug works on Linux, macOS, Windows (within WSL), Android (within Termux)**

## Example usage

Add the following to your `.zshrc`

```zsh
# Example install of plugins
plug "zap-zsh/supercharge"
plug "zsh-users/zsh-autosuggestions"

# Example install of a plugin pinned to specifc commit or branch, just pass the git reference
plug "zsh-users/zsh-syntax-highlighting" "122dc46"

# Example install of a theme
plug "zap-zsh/zap-prompt"

# Example install of a zsh completion
plug "esc/conda-zsh-completion"
```

You can also use `Zplug` to install custom plugins or source custom files present on your local filesystem. A file descriptor which points to a directory is treated as a plugin, versus a regular file. For example:

```zsh
# Example install of a local plugin
plug "$HOME/plugins/my-custom-prompt"

# Example sourcing of local files
plug "$HOME/.config/zsh/aliases.zsh"
plug "$HOME/.config/zsh/exports.zsh"
```

By default `Zplug` when installing a plugin will clone a GitHub repository using a HTTPS web URL, if you require to be able to install from a private GitHub or from a different git server (for example GitLab) you can provide a different URL prefix to be used. For example:

```zsh
# Example globally setting the prefix for Zplug to git clone using an SSH key
export ZAP_GIT_PREFIX="git@github.com:"
plug "zap-zsh/private-repo"

# Example git clone using GitLab for a single plugin
ZAP_GIT_PREFIX="https://gitlab.com/" plug "user/repo"
```

It is possible to call `plug` in any interactive shell session to source a file or to download and source a plugin for that particular session.

:warning: If you call `plug` outside your `.zshrc` file, the plugin you sourced will not be sourced at the next shell reload.

## Commands

Zplug provided commands for updating and cleaning up plugins

- To update plugins or Zplug:

  ```zsh
  zap update self # Update the Zap installation
  zap update plugins # Update all your plugins but not Zap
  zap update all # Update both the Zap installation and its plugins
  ```

- To list all plugins you are using:

  ```zsh
  zap list
  ```

- To remove plugins you are no longer using:

  ```zsh
  zap clean
  ```

## Uninstall

To uninstall Zplug, when currently active, execute the following:

```zsh
rm -rf "$ZAP_DIR"
```

When not currently active, execute the following:

```zsh
rm -rf "${XDG_DATA_HOME:-$HOME/.local/share}/zap"
```

## Notes

For sourcing local files use `$HOME` instead of `~` when giving a full path to the file.

---

**Zplug is a fork of Zap**

## Thanks to all contributors of zap

<a href="https://github.com/zap-zsh/zap/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=zap-zsh/zap" />
</a>

</div>
