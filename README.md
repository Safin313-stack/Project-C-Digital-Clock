<div align="center">

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:0f2a0f,100:1a4a1a&height=200&section=header&text=Digital+Clock+in+C&fontSize=52&fontColor=39ff14&fontAlignY=38&desc=Real-time+terminal+clock+with+12/24+hour+format+and+date+display&descAlignY=60&descSize=14&descColor=7fff7f" width="100%"/>

<br/>

[![C](https://img.shields.io/badge/Language-C-00599C?style=flat-square&logo=c&logoColor=white)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=flat-square&logo=windows&logoColor=white)]()
[![Compiler](https://img.shields.io/badge/Compiler-MinGW%20GCC-f97316?style=flat-square)](https://www.mingw-w64.org/)
[![Editor](https://img.shields.io/badge/Editor-VS%20Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white)](https://code.visualstudio.com/)
[![MIT License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square)](LICENSE)

<br/>

<a href="https://github.com/Safin313-stack/Project-C-Digital-Clock/blob/main/(PROJECT)_Digital_Clock.c">
  <img src="https://img.shields.io/badge/-%F0%9F%92%BB%20%20VIEW%20SOURCE%20%20%E2%86%92-0f2a0f?style=for-the-badge&logoColor=39ff14" alt="View Source" height="42"/>
</a>

<br/>
<sub>✦ Click above to view the full source code on GitHub ✦</sub>

<br/><br/>

</div>

---

<div align="center">

### 🕐 Features

| ⏰ Real-time Display | 🗓️ Date Display | 🔄 12/24 Format | 🖥️ Terminal UI | ⚡ system time.h |
|:---:|:---:|:---:|:---:|:---:|
| Live clock updating every second in the terminal | Shows current date alongside the time | Toggle between 12-hour AM/PM and 24-hour format | Clean formatted output directly in the console | Powered by C standard library time functions |

</div>

---

## 🖥️ Terminal Preview

```
╔══════════════════════════════════════════════╗
║                                              ║
║           DIGITAL CLOCK — C PROGRAM         ║
║                                              ║
║   ┌──────────────────────────────────────┐   ║
║   │                                      │   ║
║   │         🕐  03 : 42 : 17  PM         │   ║
║   │                                      │   ║
║   │       📅  Thursday, 19 Mar 2026      │   ║
║   │                                      │   ║
║   └──────────────────────────────────────┘   ║
║                                              ║
║   Format  : [ 12-hr ]  [ 24-hr ]             ║
║   Press   :  Ctrl+C  to exit                 ║
║                                              ║
╚══════════════════════════════════════════════╝
```

---

## 🧠 How It Works

### Fetching System Time with time.h

```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t rawtime;
    struct tm *timeinfo;

    time(&rawtime);                   // get current time as seconds since epoch
    timeinfo = localtime(&rawtime);   // convert to local time struct

    printf("Time: %02d:%02d:%02d\n",
        timeinfo->tm_hour,
        timeinfo->tm_min,
        timeinfo->tm_sec);

    printf("Date: %02d/%02d/%04d\n",
        timeinfo->tm_mday,
        timeinfo->tm_mon + 1,
        timeinfo->tm_year + 1900);

    return 0;
}
```

### 12 / 24 Hour Format Toggle

```c
int hour = timeinfo->tm_hour;
char *period = "AM";

if (hour >= 12) {
    period = "PM";
    if (hour > 12) hour -= 12;   // convert to 12-hr
} else if (hour == 0) {
    hour = 12;                   // midnight edge case
}
```

### Real-time Refresh with sleep()

```c
#include <windows.h>   // for Windows Sleep()

while (1) {
    system("cls");     // clear terminal screen
    // ... print clock ...
    Sleep(1000);       // wait 1 second then refresh
}
```

---

## 🛠️ Compile and Run

### Prerequisites
- Windows OS
- [VS Code](https://code.visualstudio.com/) + [MinGW GCC](https://www.mingw-w64.org/) installed

### Step 1 — Compile

```bash
gcc -o digital_clock "(PROJECT)_Digital_Clock.c"
```

### Step 2 — Run

```bash
./digital_clock
```

### Or run directly in VS Code terminal

```bash
# Open the folder in VS Code, then in the terminal:
gcc -o digital_clock "(PROJECT)_Digital_Clock.c" && ./digital_clock
```

> ⚠️ This project uses `windows.h` and `system("cls")` — designed for **Windows only**.
> On Linux/macOS replace `Sleep(1000)` with `sleep(1)` and `system("cls")` with `system("clear")`.

---

## 📁 Project Structure

```
Project-C-Digital-Clock/
│
├── 📄 (PROJECT)_Digital_Clock.c    ← Full source code · single file
└── 📄 README.md                    ← Project documentation
```

---

## 🛠️ Tech Stack

```
┌──────────────────────────────────────────────────┐
│              C Console Application               │
├─────────────────┬────────────────────────────────┤
│  Language       │  C (C99 standard)              │
│  Compiler       │  MinGW GCC (Windows)           │
│  Editor         │  VS Code                       │
│  Libraries      │  stdio.h · time.h · windows.h  │
│  Platform       │  Windows                       │
└─────────────────┴────────────────────────────────┘
```

---

## 📚 Key Concepts Used

```
time()         → returns current time as seconds since Jan 1, 1970
localtime()    → converts time_t to local tm struct
tm_hour        → hour field (0-23) from tm struct
tm_min         → minute field (0-59) from tm struct
tm_sec         → second field (0-59) from tm struct
tm_mday        → day of month from tm struct
tm_mon         → month (0-11, so +1 for display)
tm_year        → years since 1900 (so +1900 for display)
Sleep(1000)    → pauses execution for 1000ms (Windows)
system("cls")  → clears the terminal screen (Windows)
```

---

<div align="center">

## 👤 Developer

<br/>

**Saharia Hassan Safin**
C Developer · Front-end Developer

<br/>

[![GitHub](https://img.shields.io/badge/GitHub-Safin313--stack-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Safin313-stack)
&nbsp;
[![Source Code](https://img.shields.io/badge/Source%20Code-View%20File-0f2a0f?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Safin313-stack/Project-C-Digital-Clock/blob/main/(PROJECT)_Digital_Clock.c)

<br/>

*"Time flies — so I built a clock to watch it"* 🕐

<br/>

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a4a1a,50:0f2a0f,100:0d1117&height=120&section=footer" width="100%"/>

<sub>MIT License · © 2025 Saharia Hassan Safin · ⭐ Star this repo if it helped you!</sub>

</div>
