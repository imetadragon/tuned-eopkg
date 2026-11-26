# TuneD for Solus

Solus packaging recipe (`package.yml`) for `tuned` and `tuned-ppd`, providing system tuning profiles alongside `power-profiles-daemon` compatibility via D-Bus and Polkit.

## Installation

1. Go to the **Releases** section of this repository and download the `.eopkg` packages for **`python-linux-procfs`** and **`tuned`**.
2. Install **`python-linux-procfs`** first, then install **`tuned`**:

   ```bash
   sudo eopkg install python-linux-procfs-*.eopkg
   sudo eopkg install tuned-*.eopkg
   ```

3. Reboot your system so that D-Bus, Polkit, and `systemd` services start cleanly:

   ```bash
   sudo reboot
   ```
4. Check status
   ```bash
   sudo systemctl status tuned.service
   ```

## Uninstallation

If you want to remove TuneD and restore the default power profiles daemon:

1. Remove the `tuned` and `python-linux-procfs` packages:

   ```bash
   sudo eopkg remove tuned python-linux-procfs
   ```

2. Reinstall `power-profiles-daemon`:

   ```bash
   sudo eopkg install power-profiles-daemon
   ```

3. Reboot your system if needed to apply the changes cleanly.
