# Code Runner

Acode plugin for running code directly from acode

> [!Warning]
This plugin requires the [AcodeX-Terminal](https://acode.app/plugin/bajrangcoder.acodex) make sure you have installed and configured [AcodeX-Terminal](https://acode.app/plugin/bajrangcoder.acodex) before using this plugin

## How to use

<ul>
<li>Install plugin and <a href="https://acode.app/plugin/bajrangcoder.acodex">AcodeX-Terminal</a> </li>
<li>Start acodex terminal.</li>
<li>Click the run button to run code.</li>
<li>Hold the run button down to view/edit the command before running.</li>
</ul>

## Configure
#### Command \*.json settings example
```json
{
	"extension": "js",
	"name": "Javascipt",
	"command": "node '$name'",
	"icon": "file file_type_javascript"
}
```

#### Support Command Placeholders

`$name` -> File name

`$nameNoExt` -> Name without extension

`$dir` -> File Absolute Directory

`$dirNoSlash` -> File Directory without ending slash

`$uri` -> File Uri

`$workspaceUrl` -> Folder which the file belongs to.

`$workspace` -> Get Root Project Directory Path

## API Library for Developers

```javascript
let runner = acode.require("code.runner");

// Function Handler
runner.addHandler({
  name: "python",
  extension: "py",
  match: "*.py",
  icon: "file file_type_python",
  handler(file) {
    if (useIpython) {
      return `cd $dir && ipython ${file.name}`;
    } else {
      return `cd $dir && python ${file.name}`;
    }
  },
});

// String handler
runner.addHandler({
  name: "javascript",
  extension: "js",
  icon: "javascript",
  command: "node $path",
});

// Remove handlers.
runner.removeHandler("javascipt");

runner.addHandler({
  name: "NPM",
  match(file) {
    return file.name == "package.json";
  },
  handler(file) {
    return "npm run";
  },
});

// Use this syntax if you want to use code runner.
function main(runner) {
  runner.addHandler({
    ...
  });
}

let runner = acode.require("code.runner");
if (runner) {
  return main(runner);
} else {
  let handler = ({ detail }) => {
    if (detail.name == "coderunner") {
      main(acode.require("code.runner"));
      document.removeEventListener("plugin.install", handler);
    }
  };
  document.addEventListener("plugin.install", handler);
}
```

### Add Handler

`runner.addHandler` accepts an object with the following keys:

`name`: Name to be displayed if multiple handlers are found.

`icon`: Icon to be displayed if multiple handlers are found.

`extension`: File extension (optional).

`match`: Regex string or function (sync or async) to be matched with the file name or called with the file.

`handler`: Function (sync or async) called with `editorManagee.activeFile`, which should return the command (string).

`command`: String command used to run the file.

> **Note** Backup your commands before updating this plugin. Commands are moved to a `commands.json` file. You can edit the file through the run button `Edit commands` option.
