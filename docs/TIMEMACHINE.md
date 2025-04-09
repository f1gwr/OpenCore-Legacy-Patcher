# Restoring Time Machine backup or Migration Assistant transfer

OCLP automatically installs root patches when installing from the USB drive for the first time to ensure smooth operation of the first time settings.

Do not change the user name that was previously used in the backup (otherwise you'll get into Forbidden Access issues)

However, as an unfortunate side effect, restoring via Time Machine breaks while root patches are installed and restoring a root patched machine requires a few tricks to avoid a kernel panic.

To ensure a smooth Time Machine restore, follow the steps listed under:

1. In first time settings (Setup Assistant), do not restore the backup. Instead do all settings like you would want to start fresh.
2. Once you reach desktop, open the OCLP application and revert root patches in the Post Install Volume Patches section.
3. Restart your machine.
   * Note: Your Mac will feel slow due to lack of graphics drivers and resolution may be wrong. WiFi will also be unavailable in most cases, if your backup is on a network drive, use Ethernet.
3b. If you need to split your system into two drives, e.g. one for the system (SSD?) and one for big and/or numerous files (platter ++TB HD) first change Home location by unlocking user's preference and then option-right-click your user account and select the new Home location on the platter disk. Restart. Don't care about Applications missing in the Dock or non-working.
4. Login and start Migration Assistant.
4b. However in the two disks case do NOT select the old Home folder; only all the others (generally speaking): Applications, Other Files, System Files
6. Go through the restoring process.
7. Once finished, go into the OCLP app and reinstall the root patches.

Now you should be fully restored with Time Machine and also running with all patches.


::: warning Sequoia Note

Time Machine restoring seems to be currently broken on Sequoia even after uninstalling root patches, leading to a loop with "Migration Finished" window. Currently the only way is to restore on older OS and then upgrade to Sequoia.

:::

