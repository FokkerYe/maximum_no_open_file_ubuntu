# Ubuntu-File-Limit-Optimization

## Step 1: Update User's Bash Configuration

1. Open your user's Bash configuration file using the following command:
   ```bash
   nano ~/.bashrc
2. Add the following line to set the maximum number of open file descriptors (ulimit -n) to 8192:
   ```bash
   ulimit -n 8192
   ```
3.Save the changes and exit the editor.

4.To apply the changes to your current session, run
```bash
source ~/.bashrc

```
## Step 2: Update System Limits Configuration
1.Open the system's limits configuration file using the following command:
```bash
sudo nano /etc/security/limits.conf

```
2.Add the following lines to set the maximum number of open file descriptors (nofile) to 8192 for all users:
```bash
*    hard    nofile    8192
*    soft    nofile    8192

```
3. Save the changes and exit the editor.

4. Open the PAM (Pluggable Authentication Modules) common session configuration file using the following command
```bash
sudo nano /etc/pam.d/common-session

```
5.Ensure that the following line is present in the file:
```bash
session    required   pam_limits.so

```
6.Save the changes and exit the editor.
## Step 3: Apply Changes and Restart
1.To apply the changes, reboot your system:
```bash
reboot
```


