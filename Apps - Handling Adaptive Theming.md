# [[Apps - Handling Adaptive Theming]]

### VSCode

- Set `window.autoDetectColorScheme=true`, to enable system theme detection
- Use `workbench.preferredLightColorTheme` and `workbench.preferredDarkColorTheme` to customize individual theme states
- REF: [stackexchange.com - macos - How do I sync the Visual Studio Code (vscode) theme to use my OS light/dark color scheme? - Ask Different](https://apple.stackexchange.com/questions/381962/how-do-i-sync-the-visual-studio-code-vscode-theme-to-use-my-os-light-dark-colo)

### Google Chrome

- Go to Settings > Appearance > "Mode" and set it to "Device" to enable system theme detection
  - This will enable the browser to also send the detected theme state as a hint to webpages
  - Webpages can use media queries to detect dark versus light theming

### Obsidian
