# VS Code GH Copilot

## About GitHub Copilot in Visual Studio Code

If you use Visual Studio Code, GitHub Copilot can autocomplete code as you type. After installation, you can enable or disable GitHub Copilot, and you can configure advanced settings within Visual Studio Code or on GitHub.com.

## Prerequisites

To configure GitHub Copilot in Visual Studio Code, you must install the GitHub Copilot plugin. For more information, see "[Getting started with GitHub Copilot in Visual Studio Code](https://docs.github.com/en/copilot/getting-started-with-github-copilot/getting-started-with-github-copilot-in-visual-studio-code)."

## Keyboard Shortcuts for GitHub Copilot

You can use the default keyboard shortcuts in Visual Studio Code when using GitHub Copilot. Alternatively, you can rebind the shortcuts in the Keyboard Shortcuts editor using your preferred keyboard shortcuts for each specific command. You can search for each keyboard shortcut by command name in the Keyboard Shortcuts editor.

| Action | Shortcut | Command name |
| :-- | :-- | :-- |
| Accept an inline suggestion | Tab | editor.action.inlineSuggest.commit |
| Dismiss an inline suggestion | Esc | editor.action.inlineSuggest.hide |
| Show next inline suggestion | Option (⌥)+]  
 | editor.action.inlineSuggest.showNext |
| Show previous inline suggestion | Option (⌥)+[  
 | editor.action.inlineSuggest.showPrevious |
| Trigger inline suggestion | Option (⌥)+\  
 | editor.action.inlineSuggest.trigger |
| Open GitHub Copilot (additional suggestions in separate pane) | Ctrl+Return | github.copilot.generate |
| Toggle GitHub Copilot on/off | *No default shortcut* | github.copilot.toggleCopilot |

| Action | Shortcut | Command name |
| :-- | :-- | :-- |
| Accept an inline suggestion | Tab | editor.action.inlineSuggest.commit |
| Dismiss an inline suggestion | Esc | editor.action.inlineSuggest.hide |
| Show next inline suggestion | Alt+] | editor.action.inlineSuggest.showNext |
| Show previous inline suggestion | Alt+[ | editor.action.inlineSuggest.showPrevious |
| Trigger inline suggestion | Alt+\ | editor.action.inlineSuggest.trigger |
| Open GitHub Copilot (additional suggestions in separate pane) | Ctrl+Enter | github.copilot.generate |
| Toggle GitHub Copilot on/off | *No default shortcut* | github.copilot.toggleCopilot |

| Action | Shortcut | Command name |
| :-- | :-- | :-- |
| Accept an inline suggestion | Tab | editor.action.inlineSuggest.commit |
| Dismiss an inline suggestion | Esc | editor.action.inlineSuggest.hide |
| Show next inline suggestion | Alt+] | editor.action.inlineSuggest.showNext |
| Show previous inline suggestion | Alt+[ | editor.action.inlineSuggest.showPrevious |
| Trigger inline suggestion | Alt+\ | editor.action.inlineSuggest.trigger |
| Open GitHub Copilot (additional suggestions in separate pane) | Ctrl+Enter | github.copilot.generate |
| Toggle GitHub Copilot on/off | *No default shortcut* | github.copilot.toggleCopilot |

## Rebinding Keyboard Shortcuts

If you don't want to use the default keyboard shortcuts in Visual Studio Code when using GitHub Copilot, you can rebind the shortcuts in the Keyboard Shortcuts editor using your preferred keyboard shortcuts for each specific command.

1. Click the **File** menu, click **Preferences**, then click **Keyboard Shortcuts**. ![Screenshot of Visual Studio Code keyboard shortcuts](https://docs.github.com/assets/cb-77431/images/help/copilot/vsc-keyboard-shortcuts.png)
2. In the "Keyboard Shortcuts" editor, search for the command name of the keyboard shortcut you want to change. ![Screenshot of Keyboard shortcut search bar](https://docs.github.com/assets/cb-1143/images/help/copilot/vsc-shortcut-search-bar.png)
3. Next to the command you want to change, click the pencil icon. ![Screenshot of Keyboard shortcut editor](https://docs.github.com/assets/cb-30027/images/help/copilot/vsc-edit-shortcuts.png)
4. Type the keystrokes you want to use for the command, then press Enter/Return. ![Screenshot of Edit keyboard shortcut textbox](https://docs.github.com/assets/cb-1224/images/help/copilot/vsc-edit-shortcuts-textbox.png)

## Enabling or Disabling GitHub Copilot

You can enable or disable GitHub Copilot from within Visual Studio Code. The GitHub Copilot status icon in the bottom panel of the Visual Studio Code window indicates whether GitHub Copilot is enabled or disabled. When enabled, the background color of the icon will match the color of the status bar. When disabled, the background color of the icon will contrast with the color of the status bar.

1. To enable or disable GitHub Copilot, click the status icon in the bottom panel of the Visual Studio Code window. ![Screenshot of the status icon in Visual Studio Code](https://docs.github.com/assets/cb-13418/images/help/copilot/status-icon-visual-studio-code.png)

2. If you are disabling GitHub Copilot, you will be asked whether you want to disable suggestions globally, or for the language of the file you are currently editing.

    - To disable suggestions from GitHub Copilot globally, click **Disable Globally**.
    - To disable suggestions from GitHub Copilot for the specified language, click **Disable for *LANGUAGE***. ![Screenshot of option to disable GitHub Copilot globally or for the current language](https://docs.github.com/assets/cb-41945/images/help/copilot/disable-copilot-global-or-langugage.png)

## Enabling or Disabling Inline Suggestions

You can choose to enable or disable inline suggestions for GitHub Copilot in Visual Studio Code.

1. In the **File** menu, navigate to **Preferences** and click **Settings**. ![Screenshot of Visual Studio Code settings](https://docs.github.com/assets/cb-77040/images/help/copilot/vsc-settings.png)
2. In the left-side panel of the settings tab, click **Extensions** and then select **Copilot**.
3. Under "Inline Suggest:Enable", select or deselect the checkbox to enable or disable inline suggestions.

## Enabling or Disabling GitHub Copilot for Specific Languages

You can specify which languages you want to enable or disable GitHub Copilot for.

1. From the Visual Studio Code, click the **Extensions** tab, then navigate to the **Copilot** section. For more information, see "[Enabling and disabling inline suggestions](https://docs.github.com/en/copilot/configuring-github-copilot/configuring-github-copilot-in-visual-studio-code#enabling-and-disabling-inline-suggestions)."

2. Under "Enable or disable Copilot for specified languages", click **Edit in settings.json**.

3. In the *settings.json* file, add or remove the languages you want to enable or disable GitHub Copilot for. For example, to enable Python in GitHub Copilot, add `"python": true` to the list, ensuring there is a trailing comma after all but the last list item.

    ```json
    {
        "editor.inlineSuggest.enabled": true,
        "github.copilot.enable": {
            "*": true,
            "yaml": false,
            "plaintext": false,
            "markdown": true,
            "javascript": true,
            "python": true
        }
    }
    ```

## Configuring GitHub Copilot Settings on GitHub.com

Once you have an active GitHub Copilot trial or subscription, you can adjust GitHub Copilot settings for your personal account on GitHub in the [GitHub Copilot settings](https://github.com/settings/copilot). The settings apply anywhere that you use GitHub Copilot. You can configure the suggestions that GitHub Copilot offers and how GitHub uses your telemetry data.

## Enabling or Disabling Duplication Detection

GitHub Copilot includes a filter which detects code suggestions matching public code on GitHub. You can choose to enable or disable the filter. When the filter is enabled, GitHub Copilot checks code suggestions with their surrounding code of about 150 characters against public code on GitHub. If there is a match or near match, the suggestion will not be shown to you.

1. In the upper-right corner of any page, click your profile photo, then click **Settings**.

    ![Settings icon in the user bar](https://docs.github.com/assets/cb-34573/images/help/settings/userbar-account-settings.png)

2. In the left sidebar, click **GitHub Copilot**.

3. Under **Suggestions matching public code**, select the dropdown menu, then click **Allow** to allow suggestions matching public code, or **Block** to block suggestions matching public code. ![Screenshot of duplication detection option](https://docs.github.com/assets/cb-10101/images/help/copilot/duplication-detection.png)

4. To confirm your new settings, click **Save**.

## Enabling or Disabling Telemetry

You can choose whether your code snippets are collected and retained by GitHub and further processed and shared with Microsoft and OpenAI by adjusting your user settings. For more information about data that GitHub Copilot may collect depending on your telemetry settings, see "[GitHub Terms for Additional Products and Features](https://docs.github.com/en/free-pro-team@latest/site-policy/github-terms/github-terms-for-additional-products-and-features#github-copilot)" and the [GitHub Copilot privacy FAQ](https://github.com/features/copilot/#faq-privacy).

1. In the upper-right corner of any page, click your profile photo, then click **Settings**.

    ![Settings icon in the user bar](https://docs.github.com/assets/cb-34573/images/help/settings/userbar-account-settings.png)

2. In the left sidebar, click **GitHub Copilot**.

3. To allow or prevent GitHub using your telemetry data, select or deselect **Allow GitHub to use my code snippets for product improvements**. ![Screenshot of telemetry option](https://docs.github.com/assets/cb-33160/images/help/copilot/telemetry-option.png)

4. To confirm your new settings, click **Save**.
