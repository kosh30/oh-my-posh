# Contributing

Note we have a code of conduct, please follow it in all your interactions with the project.

**Note:** Theme aditions are no longer accepted due to the ever growing set. We do however
accept showcasing your custom theme in the [themes discussion section here][themes-discussion]
or the [themes channel on Discord][discord-link].

Ensure you've read through the [documentation][docs] so you understand the core concepts of the
project. If you're looking to get familiar with go, following the getting started [guide][guide]
can be a good starting point.

## Pull Request Process

1. Ensure any dependencies or build artifacts are removed/ignored before creating a commit.
2. Commits follow the [conventional commits][cc] guidelines.
(You can [look up the supported *types*][cc-types] along with an explanation [in the documentation][cc-types])
3. Update the documentation with details of changes to the functionality, this includes new segments
   or core functionality.
4. Pull Requests are merged once all checks pass and a project maintainer has approved it.

## Codespaces / Devcontainer Development Environment

Arguably the easiest way to contribute anything is to use our prepared development environment.

We have a `.devcontainer/devcontainer.json` file, meaning we are compatible with:

- [![Open in GitHub Codespaces][codespaces-badge]][codespaces-link], or
- the [Visual Studio Code Remote - Containers][devcontainer-ext] extension.

This Linux environment includes all shells supported by oh-my-posh, including Bash, ZSH,
Fish and PowerShell, the latter of which is the default.

### Configuring Devcontainer's Timezone & Theme

1. Open the `.devcontainer/devcontainer.json` file and in the "*build*" section modify:

   - `TZ`: with [your own timezone][timezones]

2. Summon the Command Panel (Ctrl+Shift+P) and select `Codespaces: Rebuild Container`
   to rebuild your devcontainer. (This should take just a few seconds.)

### Recompiling oh-my-posh

The devcontainer definition preinstalls the latest stable oh-my-posh release at build time.

To overwrite the installation's version inside the running devcontainer, you may use the
VSCode *task* `devcontainer: build omp` to rebuild your oh-my-posh with that of
your running repository's state. (You might see a button for this in your statusbar.)

If the compile succeeds, `oh-my-posh --version` should reply:
`development`

Should you somehow mess up your devcontainer's OMP install catastrophically, remember that
if you do `Codespaces: Rebuild Container` again, you'll be back to the latest stable release.

## Local development

Make sure your local go version matches with the pinned version in [go.mod]. You can build
oh-my-posh by navigating the to the `/src` folder and executing the following command.

```bash
go build -v -o /path/to/oh-my-posh(.exe)
```

### Running tests

To execute the tests, run the following command from the `/src` folder.

```bash
go test "./..."
```

[themes-discussion]: [https://github.com/JanDeDobbeleer/oh-my-posh/discussions/categories/themes]
[discord-link]: [https://discord.com/channels/1023597603331526656/1055533233309233252]
[docs]: <https://ohmyposh.dev/docs>
[guide]: <https://ohmyposh.dev/docs/contributing/started>
[cc]: <https://www.conventionalcommits.org/en/v1.0.0/#summary>
[cc-types]: <https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/.commitlintrc.yml#L23-L33>
[codespaces-badge]: <https://github.com/codespaces/badge.svg>
[codespaces-link]: <https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=175405157>
[devcontainer-ext]: <https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers>
[timezones]: <https://en.wikipedia.org/wiki/List_of_tz_database_time_zones>
[go.mod]: src\go.mod
