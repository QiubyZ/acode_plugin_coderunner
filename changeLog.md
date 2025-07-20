# Updates

## `v1.1.6`

> fixed path for default terminal

<details>
  <summary>
    <code><strong>v1.1.4</strong></code>
  </summary>
  <ul>
    <li>Add $workspace</li>
  </ul>
</details>

<details>
  <summary>
    <code><strong>v1.1.3</strong></code>
  </summary>
  <ul>
    <li>Added 'icon' to handlers, fixed bugs, better command editing.</li>
    <li>Added 'Acode Terminal' backend, Fixed 'AcodeX' backend.</li>
    <li>Moved commands to `commands.json`.</li>
  </ul>
</details>

<details>
  <summary>
    <code><strong>v1.1.2</strong></code>
  </summary>
  <ul>
    <li>Added 'plugin.install' event listener so other plugins know when code runner is installed if not already installed. Use `event.target.detail.name == 'coderunner'` to check if the installed plugin is acode sdk.</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.1.0, v1.1.1</strong></code>
  </summary>
  <ul>
    <li>Updated apis</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.8, 1.0.9</strong></code>
  </summary>
  <ul>
    <li>Bug fixes</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.7</strong></code>
  </summary>
  <ul>
    <li>Added ability to run projects (based on the content of the workspace directory). E.g: Opening a folder with the file 'package.json' allows you to run the 'NPM' project which gives you the optikn to select from the scripts defined in 'package.json'. Opening a project with 'manage.py' allows you to run the 'django' project.</li>
    <li>Added option to select between built-in runner (acode) or using terminal.</li>
    <li>Added option to disable Projects runner in settings.</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.6</strong></code>
  </summary>
  <ul>
    <li>Changed commands structure from [extension, command] to { name: string, extension: string or match: regex | string | function, handler: function or command: string }</li>
    <li>Removed `addWildcard` and `removeWildcard` functions use `addHandler` with match function instead</li>
    <li>Added ability to select between multiple handler natches.</li>
    <li>Added setting to replace default run button</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.5</strong></code>
  </summary>
  <ul>
    <li>Added option to edit and add commands from settings page</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.3, v1.0.4</strong></code>
  </summary>
  <ul>
    <li>Bug fixes</li>
    <li>Ability to run package.json scripts</li>
  </ul>
</details>
<details>
  <summary>
    <code><strong>v1.0.2</strong></code>
  </summary>
  <ul>
    <li>Added keyboard shortcut <kbd>ctrl+r</kbd></li>
    <li>Alerts you if acodex is not installed.</li>
    <li>Logs to "Acode SDK" logger if installed.</li>
    <li>Supports up to 30 languages</li>
  </ul>
</details>
