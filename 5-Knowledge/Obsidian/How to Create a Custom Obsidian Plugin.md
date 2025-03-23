# How to Create a Custom Obsidian Plugin

> [!note] Getting Started
> Obsidian plugins are a powerful way to personalize your Obsidian experience and add features specific for your workflow. You mainly need some JS knowledge.
> - [ ] Review this guide and tailor it to your development preferences
> - [ ] Recommended: Fork the `obsidian-plugin-template` repo and [personalize it](https://github.com/stracker-phil/obsidian-plugin-template/commit/0fca14e5ffce404b545274676dca01f91cac45bc)

Obsidian plugins are JavaScript files that are described by a manifest-file. Optionally, a plugin can also contain a CSS file which is loaded when the plugin is active.

The most basic plugin requires two files:

- `script.js` The plugin itself
- `manifest.json` Meta details, used by Obsidian

**Remember**: Always develop and test plugins in a Sandbox vault, as bugs can corrupt the vault or mess with the notes! Hit `⌘ P` and choose `Open another vault` and open the "Sandbox" vault, located at `~/Obsidian/Sandbox`.

## Quick Start Using a Template

Source: https://docs.obsidian.md/Plugins/Getting+started/Build+a+plugin
Template Repo: https://github.com/stracker-phil/obsidian-plugin-template

```shell
# Create a new plugin in my dev environment.
cd ~/Coding/Obsidian
git clone git@github.com:stracker-phil/obsidian-plugin-template myplugin
cd myplugin

# Link the plugin to my sandbox vault
ln -s "$(pwd)/dist" ~/Obsidian/Sandbox/.obsidian/plugins/myplugin

# Personalize the plugin
git remote remove origin
gh repo create obsidian-myplugin --private --source=. --push

edit manifest.json                 # Change id, name, description
edit package.json                  # Change name, description
edit .github/workflows/release.yml # Change plugin.zip to the plugin id

# Build the sample plugin
npm install
npm run build
```

### Verify The Setup Works

Open the Sandbox vault (or reload it), open the settings and check if the new plugin shows up on the "Community plugins" page.

### Distribute the Plugin

Add a new tag to the plugin and push it to the GitHub repo. The included GitHub action fires when a new tag is pushed and creates a full release item with all relevant files.

To increase the plugin version and create a new tag run one of the following commands:

```sh
npm run version patch
npm run version minor
npm run version major
```

> [!note]- Tag format
> All tags in the plugin repo should follow a semantic version, containing only digits and exactly 2 dots:
> - ok: `0.0.1`, `1.0.0`, `1.0.13`
> - bad: `v1.0.0`, `1.0`, `1.0.0-alpha`

## Sample Plugin

https://github.com/stracker-phil/obsidian-personal-api/
