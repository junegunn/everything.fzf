<h1 align="center">
  <i>everything</i>.fzf
</h1>

![everything.fzf](https://github.com/junegunn/i/blob/master/everything.fzf.jpg)

What is this?
-------------

A personal collection of simple scripts that integrate *everything* with fzf.

They are mostly opinionated, unpolished, unextendable, inconsistent, and
unconfigurable — just the way I like them. Only tested on my MacBook.
Keep that in mind.

Hope you find some ideas useful.

How to use
----------

Each script is self-contained and can be run directly and individually.
You can add the repository to your `$PATH`,

```sh
[[ $PATH =~ everything.fzf ]] || PATH="/path/to/everything.fzf:$PATH"
```

or copy/symlink only the ones you like.

Prerequisites
-------------

The scripts are written in Bash and Ruby, so both are required.

Some scripts also depend on the following programs:

* bat
* chrome-cli
* figlet
* gh
* mise
* ripgrep

```sh
brew install bash ruby bat chrome-cli figlet gh mise ripgrep
```

Scripts
-------

### [_apps_](https://www.apple.com/macos)[.fzf](apps.fzf)

* Select macOS applications to open

### [_chrome_](https://www.google.com/chrome/)[.fzf](chrome.fzf)

* `chrome.fzf [t|h|b]`
    * `t` for open tabs (default; requires `chrome-cli`)
        * You can press `CTRL-W` to close a tab
    * `h` for history
    * `b` for bookmarks

### [_claude_](https://www.claude.com/product/claude-code)[.fzf](claude.fzf)

* Browse prompts from `~/.claude/history.jsonl`
* Press enter to resume the session or switch to the tmux pane running the
  session

### [_docker_](https://www.docker.com/)[.fzf](docker.fzf)

* List running containers with memory usage
* Preview container logs in the bottom pane
* Press `CTRL-S` to stop a container, `CTRL-T` to show stats and top
* Press `CTRL-O` to open full logs in your editor

### [_figlet_](http://www.figlet.org/)[.fzf](figlet.fzf)

* Type in text, select a font, preview the result, and press enter to copy it
  to the clipboard.
* Use `/` to separate the text from a search query
  (e.g. `hello / banner` to preview "hello" while filtering for fonts matching
  "banner"). If there is no `/`, the whole query is used as the text.

### [_gist_](https://gist.github.com/)[.fzf](gist.fzf)

* Press enter on a gist to edit it in your editor
* To access gists on GitHub Enterprise, set the `GH_HOST` environment variable
  ```sh
  alias giste.fzf='GH_HOST=git.evil.com gist.fzf'
  ```

### [_jira_](https://www.atlassian.com/software/jira)[.fzf](jira.fzf)

```
Usage: jira.fzf URL [JQL|PROJECT...]
    -u, --user={USER:PASSWORD,PAT}   User name and password (user:password) or PAT
    -q, --query=QUERY                Initial query
        --lines=NUM_LINES            Number of lines of description to show
        --limit=MAX_ITEMS            Maximum number of items to fetch
```

```sh
jira.fzf --limit 1000 --lines 10 https://issues.apache.org/jira \
    'creator = junegunn order by updated desc'
```

### [_kube_](https://kubernetes.io/)[.fzf](kube.fzf)

```
usage: kube.fzf [p|d|j|cj|sc|sn]
  p   list all pods
  d   list all deployments
  j   list all jobs
  cj  list all cronjobs
  sc  switch to a different context
  sn  switch to a different namespace
```

### [_maccy_](https://maccy.app/)[.fzf](maccy.fzf)

* You probably don't need this unless you really need to browse your clipboard
  history with more screen estate.
* You can press `CTRL-E` to edit the selected item in your editor

### [_make_](https://www.gnu.org/software/make/)[.fzf](make.fzf)

* Select Makefile targets to run

### [_mise_](https://mise.jdx.dev/)[.fzf](mise.fzf)

* First select a tool, then select a version of it to use it

### [_pr_](https://docs.github.com/en/pull-requests)[.fzf](pr.fzf)

* Browse and check out a GitHub pull request for the current repository
* Press `CTRL-V` to view the pull request in Vim
* Press `CTRL-O` to open the pull request in your browser

### [_pr-by_](https://docs.github.com/en/pull-requests)[.fzf](pr-by.fzf)

* Search GitHub pull requests by a specific user across all repositories
* Press `CTRL-V` to view the pull request in Vim
* Press `CTRL-O` to open the pull request in your browser

```sh
# usage: pr-by.fzf [--limit=N] <author> [fzf-args]
pr-by.fzf junegunn
```

### [_rg_](https://github.com/BurntSushi/ripgrep)[.fzf](rg.fzf)

* See https://junegunn.github.io/fzf/tips/ripgrep-integration/

### [_ssh_](https://en.wikipedia.org/wiki/Secure_Shell)[.fzf](ssh.fzf)

* Select known hosts to open SSH connections to them in a tiled tmux split
  panes

### [_wiki_](https://www.atlassian.com/software/confluence)[.fzf](wiki.fzf)

* Browse recently viewed and modified pages in Confluence wiki
  ```
  Usage: wiki.fzf URL
      -u, --user={USER:PASSWORD,PAT}   User name and password (user:password) or PAT
  ```

What else?
----------

* https://github.com/junegunn/fzf-git.sh
* https://github.com/junegunn/tmux-fzf-url
* https://github.com/junegunn/tmux-fzf-maccy

LICENSE
-------

MIT
