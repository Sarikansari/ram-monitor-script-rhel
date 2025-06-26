### ✅ GitHub Repository Name:

`ram-monitor-script-rhel`

---

### 📄 Description (for GitHub):

> A simple Bash script developed for **Red Hat Enterprise Linux (RHEL)** systems that monitors available RAM. It checks the current available RAM size and issues a warning if it falls below a defined threshold. Ideal for lightweight system monitoring or cron-based alerts in production/testing environments.

---

### 📁 Project Structure

```
ram-monitor-script-rhel/
├── ram_check.sh
└── README.md
```

---

### 📜 Script: `ram_check.sh`

```bash
#!/bin/bash

FREE_SPACE=$(free -mt | grep "Total" | awk '{print $4}')
TH=500

if [[ $FREE_SPACE -lt $TH ]]
then
    echo "WARNING, RAM is running low"
else
    echo "RAM Space is sufficient - $FREE_SPACE M"
fi
```

---

### ⚙️ How it works

* The script uses `free -mt` to display memory usage in megabytes.
* It filters the "Total" memory line using `grep`.
* Then, it uses `awk` to extract the 4th column (Available RAM).
* Compares available memory to a threshold (e.g., `500 MB`).
* Displays a warning if available memory is below the threshold.

---

### 🧪 Sample Output

```bash
[root@localhost projects]# free -mt | grep "Total"
Total:          5694        1525        3383
[root@localhost projects]# free -mt | grep "Total" | awk '{print $4}'
3383
[root@localhost projects]# ./ram_check.sh
RAM Space is sufficient - 3383 M
```

---

### 📝 Usage

1. Make the script executable:

```bash
chmod +x ram_check.sh
```

2. Run the script:

```bash
./ram_check.sh
```

---

### 📌 Notes

* Customize the threshold value by changing the `TH=500` line.
* Can be integrated with a **cron job** for periodic checks and notifications.

---

Let me know if you’d also like me to help generate the actual GitHub repo structure with the files (e.g., a ZIP or downloadable package).
