
## 📅 Create a Daily Scheduled Task

```cmd
schtasks /create /sc daily /tn "MyDailyTask" /tr "C:\Path\To\YourProgram.exe" /st 13:37
```

**Parameters:**

* `/sc daily` — Run daily
* `/tn` — Task name
* `/tr` — Task to run (program or script)
* `/st` — Start time (24-hour format, e.g. 13:37)

---

## ⚙️ Optional Flags

| Flag             | Description                                             |
| ---------------- | ------------------------------------------------------- |
| `/ru SYSTEM`     | Run as SYSTEM (no login required)                       |
| `/ru <username>` | Run under a specific user account                       |
| `/rl HIGHEST`    | Run with highest privileges (like Run as Administrator) |
| `/f`             | Force creation or deletion without confirmation         |

**Example:**

```cmd
schtasks /create /sc daily /tn "MyDailyTask" /tr "C:\Scripts\backup.bat" /st 13:37 /ru SYSTEM /rl HIGHEST
```

---

## 🧹 Delete a Task

```cmd
schtasks /delete /tn "MyDailyTask"
```

**Skip confirmation:**

```cmd
schtasks /delete /tn "MyDailyTask" /f
```

---

## 🔍 View Tasks

List all tasks:

```cmd
schtasks /query
```

View details for one task:

```cmd
schtasks /query /tn "MyDailyTask" /v /fo list
```

---

## 🧩 Task Types

### 1. EXE File

```cmd
/tr "C:\Program Files\MyApp\app.exe"
```

### 2. Batch or Command Script (`.bat` / `.cmd`)

```cmd
/tr "C:\Scripts\myscript.bat"
```

or explicitly:

```cmd
/tr "cmd.exe /c C:\Scripts\myscript.bat"
```

### 3. PowerShell Script (`.ps1`)

```cmd
/tr "powershell.exe -ExecutionPolicy Bypass -File \"C:\Scripts\myscript.ps1\""
```

---

## 🚫 Disable or Enable a Task

Disable:

```cmd
schtasks /change /tn "MyDailyTask" /disable
```

Enable:

```cmd
schtasks /change /tn "MyDailyTask" /enable
```

---

## 💡 Tips

* Always use **full paths**.
* Wrap paths with **spaces** in quotes.
* Use `/rl HIGHEST` if admin rights are required.
* Use `/ru SYSTEM` for background tasks when no user is logged in.

---

**Example Summary**

| Purpose                   | Example Command                                                                                                                 |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Run `.exe` daily at 13:37 | `schtasks /create /sc daily /tn "MyApp" /tr "C:\App\run.exe" /st 13:37`                                                         |
| Run `.bat` script daily   | `schtasks /create /sc daily /tn "MyBatch" /tr "cmd.exe /c C:\Scripts\run.bat" /st 13:37`                                        |
| Run PowerShell daily      | `schtasks /create /sc daily /tn "MyPS1" /tr "powershell.exe -ExecutionPolicy Bypass -File \"C:\Scripts\script.ps1\"" /st 13:37` |
