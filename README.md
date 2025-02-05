# Phishing-Reporter
An Outlook Plugin to report phishing emails easier and provides full integration with [GoPhish](https://github.com/gophish/gophish).

# Screenshots
![UI](https://www.0d.ae/bl-content/uploads/pages/7728a42b4acd7a69b0f5d83e906b07f6/topmenu.png)

![Right-click UI](https://www.0d.ae/bl-content/uploads/pages/7728a42b4acd7a69b0f5d83e906b07f6/rightclick.png)

![How it looks like](https://www.0d.ae/bl-content/uploads/pages/7728a42b4acd7a69b0f5d83e906b07f6/popup.png)

# Write-up and Guide
https://www.0d.ae/report-phishing-plugin-for-outlook

If you plan to use the plugin, please fill the 3 Questions [survey](https://forms.gle/jBWJv6o82T6kB4GD9)

# Features
- [x] Auto-deletes suspecious emails once reported.
- [x] Append [POTENTIAL PHISH] to subject for automatic Outlook rules.
- [x] Extract and list the most important information in the report email such as email headers, URLs/Ips, domains, attachments hashes, sender details.
- [x] Removes hyperlinks from suspecious links. (https:// becomes https[:]// and so on).
- [x] Attaches original email to the report for further investigation.
- [x] Full integration with the Open Source Phishing Framework, [GoPhish](https://github.com/gophish/gophish). Now you can see who reported a simulated phishing email sent by your information security team.
- [x] Two buttons for easy reporting. One in the `Home` menu. The second when you right-click an email.
- [x] Reports any bugs to a seperate support email without annoying the users.
- [x] Installer-ready: fast compile to EXE file, as all hassles were tackled already. Just follow the guide.

# Before you start:

:warning: Verify that you have `Microsoft Visual Studio Installer Projects` component installed in Visual Studio. You can install it by going to `Tools` -> `Get Tools and Features`

:warning: Make sure you build the project's installer with the right TargetPlatform for your Office. If you have Office 32-bit installed, then compile the project as 32-bit. If you have Office 64-bit, then compile the project as 64-bit. You can do so by choosing `Installer -> (from "Properties" menu) TargetPlatform -> x86 or x64`

# How-to Guide:

> Note: I used Visual Studio 2017 with .NET Framework 4.8 to compile it. The plugin was tested on Outlook 2019 (x64).
1. Download the project and extract it.
2. Double click `PhishingReporter.sln` to open the project using Visual Studio.
3. From the top menu, if it is on `Debug` mode, change configuration to `Release`.
4. In the right menu, Open `Settings.settings` and go to `Settings` Tab.
5. From there, change:
	- `client_trigram`: should be the internal client ID trigram.
6. Save the file.
7. Build the project. From the top menu `Build` → `Build PhishingReporter`.
8. In the right menu, Click `Installer` and change what you prefer on `Properties` Menu, I recommend to change:
	- Manufacturer, ManufacturerUrl, SupportPhone, SupportUrl
	- Generate a new UpgradeCode by clicking the `...` button then `New Code`.
9. [Optional] If you want to change the installation wizard splash screen:
	- Open `splash.psd` file using Photoshop, and design the splash screen you like.
	- Export the design by overwriting `splash.jpg` file in the main project directory.
10. At the end, right-click `Installer` and choose `Build`.
11. The installer file should be located in `PhishingReporter\Installer\Release` folder.

# Credits
- 0dteam
- Abdulla Albreiki
- Reused some code from [NotifySecurity](https://github.com/certsocietegenerale/NotifySecurity) project by Nicolas Chaussard
