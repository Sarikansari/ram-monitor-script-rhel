# ram-monitor-script-rhel
A simple Bash script developed for Red Hat Enterprise Linux (RHEL) systems that monitors available RAM. It checks the current available RAM size and issues a warning if it falls below a defined threshold. Ideal for lightweight system monitoring or cron-based alerts in production/testing environments.

⚙️ How it works
The script uses free -mt to display memory usage in megabytes.

It filters the "Total" memory line using grep.

Then, it uses awk to extract the 4th column (Available RAM).

Compares available memory to a threshold (e.g., 500 MB).

Displays a warning if available memory is below the threshold.

# Sample Output
![image](https://github.com/user-attachments/assets/e6316802-b049-4750-82ea-c398df93aa38)


