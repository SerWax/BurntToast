# Full Change Log

- [v0.7.2](https://github.com/Windos/BurntToast/releases/download/v0.7.2/BurntToast.zip)

  - Fix: Curly Braces when "Reminder" pops up ([#72](https://github.com/Windos/BurntToast/issues/72))

  - Fix: Caching remote gifs are saved based on their remote filename and not overwritten ([#105](https://github.com/Windos/BurntToast/issues/105))

    - Thanks [@KelvinTegelaar](https://github.com/KelvinTegelaar)

  - Fix: BurntToast and .NET 5 ([#101](https://github.com/Windos/BurntToast/issues/101))

- [v0.7.1](https://github.com/Windos/BurntToast/releases/download/v0.7.1/BurntToast.zip)

  - Update: Microsoft Community Toolkit to 6.0.0

  - New: Support relative paths on images

  - New: "ScheduledToast" switch added to `Get-BTHistory` which returns scheduled or snoozed toast notifications

  - Enhancement: Libraries only loaded on module import if libraries not already loaded

  - Enhancement: Validate that image paths exist

  - Fix: Reverted to XML clean up to remove curly braces if databindings are not being used (Issue #72)

  - Known Issues:

    - Regardless of what snooze option is chosen, a snoozed toast will re-appear after 9 minutes
    - Cause is unknown and isn''t unique to v0.7.1, will be investigated while working on v0.7.2

- [v0.7.0](https://github.com/Windos/BurntToast/releases/download/v0.7.0/BurntToast.zip)

  - **HEADLINE FEATURE**: My People "Shoulder Tap" notifications have been implemented

  - You can now specify images on the network via UNC paths. Fix for #56

  - We're now properly supporting bindable text, and removing the curly braces more gracefully.

  - Get a list of all toasts you've sent, which have not been dismissed by the user, using `Get-BTHistory`.

  - Remove toasts you've sent, using `Remove-BTNotification`.

  - Set expiration times on toasts using the new `ExpirationTime` parameter on `New-BurntToastNotification` and `Submit-BTNotification`.

    - Toasts which have expired are removed from the Action Center.

  - Send toasts directly to the Action Center, and avoid showing them on screen, with the new `SuppressPopup` switch on `New-BurntToastNotification` and `Submit-BTNotification`.

  - You can now adjust a toasts timestamp (both past and future) using the `CustomTimestamp` parameter on `New-BurntToastNotification` and `New-BTContent`.

    - If not specified, the system uses the time at which the toast was received and this may not accuratly reflect the intent of the notification.

- [v0.6.3](https://github.com/Windos/BurntToast/releases/download/v0.6.3/BurntToast.zip)

  - Update Windows Community Toolkit (UWP Notifications) to 5.0.0.

    - Also switched to the UAP variant, as the .NET Standard one was causing issues for some users.

  - (BACKEND) Implemented CI pester tests on Azure DevOps Pipelines, including code coverage stats.

  - Fixed style issues flagged by Codacy, mainly Markdown headers.

  - Added WhatIf support to all functions, laying ground work for expanded (read: any) Pester tests.

  - Functions all in .psm1 now, instead of separate .ps1 files. SPEED!

- [v0.6.2](https://github.com/Windos/BurntToast/releases/download/v0.6.2/BurntToast.zip)

  - Updated UWP Toolkit to 2.2.0

  - Fixed an issue with sound looping

  - New-BurntToastNotification now accepts multiple ProgressBar objects

  - Fixed Issue #28, ProgressBars should now work for all locales

  - Fixed Issue #18, Images from the internet will now be downloaded locally

    - Supports regular images, hero images, and applogo

  - All functions now included in .psm1 for release (Thanks @chrislgardner)

- [v0.6.1](https://github.com/Windos/BurntToast/releases/download/v0.6.1/BurntToast.zip)

  - Customizable AppId removed from the New-BurntToastNotification function as a quick fix for Fall Creators Update.

    - If you''re using a customized AppId and are not upgrading to the Fall Creators Update, then stay on version 0.6.0.

  - Default AppId changed to match PowerShell.exe.

  - Registry entry for AppId is now automatically created when the module loads.

  - Included UWPCommunityToolkit library updated to v2.0.0.

- [v0.6.0](https://github.com/Windos/BurntToast/releases/download/v0.6.0/BurntToast.zip)

  - Updated bundled UWP Toolkit to 1.4.1

    - Note that this caused an issue where strings were being wrapped with curly braces in end results. A workaround has been implemented, but could mean that if you legitimately use some rather obscure strings, they may have the braces removed.

  - Hero Images working now (Thanks to Creators Update)

  - Headers can now be included (Creators Update feature)

  - Progress bars can now be included (Creators Update feature)

  - Specify a unique identifier in order to replace existing toasts

  - You can specify a custom sound file using the -Path parameter of the New-BTAudio function. This hasn''t been exposed through the main function... that poor thing is getting bloated.

  - There is now help for every public function, and the online version for each of them can be found on github. Specify the -Online switch when using Get-Help to be taken directly there.

- [v0.5.2](https://github.com/Windos/BurntToast/releases/download/v0.5.2/BurntToast.zip)

  - Exposed ability to have custom buttons via New-BurntToastNotification, passing result from New-BTButton to the -Button parameter.

    - Expect a blog post soon covering some cool ways to use these buttons. Keep an eye out on [king.geek.nz](http://king.geek.nz).

  - Fixed module commands not auto-loading by removing Basic/Advanced function designation ( :( ).

  - Help created for New-BTButton, and the function has had a pass to ensure it works as per the community toolkit.

  - Help completed for New-BurntToastNotification, and Toast alias now exporting correctly.

- [v0.5.1](https://github.com/Windos/BurntToast/releases/download/v0.5.1/BurntToast.zip)

  - Small bug fixes (thanks for opening issues!)
  - Confirmed: Now **ONLY** works on Windows 10
  - BurntToast now has its own, original, logo!
  - New public function to adjust function level of module: Set-BTFunctionLevel
  - Implemented checking for and registering of AppId in the registry to ensure proper Toast behaviour in the Action Center

- [v0.5.0](https://github.com/Windos/BurntToast/releases/download/v0.5.0/BurntToast.zip)

  - Converted to using the UWP Community Toolkit.
  - Snooze and Dismiss now available and working.
  - Documentation is out of date, this will be polished in the next release.

- [v0.4.0](https://github.com/Windos/BurntToast/releases/download/v0.4.0/BurntToast.zip) - Last version that supports Windows 8

  - Credential parameter added so toasts can be generated for regular user when running PowerShell host as a different (e.g. Admin) account.

- [v0.3.0](https://github.com/Windos/BurntToast/releases/download/v0.3.0/BurntToast.zip)

  - Help has been added
  - Toasts can be silent with -Silent switch
  - General bug fixes

- [v0.2.0](https://github.com/Windos/BurntToast/releases/download/v0.2.0/BurntToast.zip)

- [v0.1.0](https://github.com/Windos/BurntToast/releases/download/v0.1.0/BurntToast.zip)