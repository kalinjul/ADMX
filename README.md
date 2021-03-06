# ADMX
Collabora Office / LibreOffice Windows Group Policy Template

For more info visit https://www.collaboraoffice.com/windows-group-policy-admx/

Pull requests are welcome. Please help with translations at [Transifex](https://www.transifex.com/collabora-productivity-ltd/collabora-office-libreoffice-windows-group-policy-template-amdx/).

### caution! 
When you add a "policy" in the admx file, add the corresponding "presentation" in all adml. Not just in your language.
Otherwise, this causes the following error for users of these adml files:

Resource "$(string.something)" referenced in attribute displayName could not be found. 
File Path\to\something.admx, line xxx, column xxx

## Localization notes
[ITS Tool](http://itstool.org) is used to extract strings from adml file, and merge them back. The very simple `adml.its` file in this repository should be copied into e.g. `/usr/local/share/itstool/its/`. It sets one `preserveSpaceRule`.

Create the pot from the adml file:

    itstool -o Collabora-Office-adml.pot Collabora-Office.adml

Merge the translated strings to the adml file:

    itstool -m Collabora-Office-adml.mo -o it-IT/ Collabora-Office.adml
