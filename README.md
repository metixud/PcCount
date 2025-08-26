# PcCount

PcCount is a small Windows console program in C++ that shows **how long your PC has been running** since the last boot.  
It calculates days, hours, minutes, and seconds using the Windows API.

---

## 📋 Code

```cpp
#include <windows.h>
#include <iostream>

int main() {
    ULONGLONG ms = GetTickCount64();

    ULONGLONG seconds = ms / 1000;
    ULONGLONG minutes = seconds / 60;
    ULONGLONG hours = minutes / 60;
    ULONGLONG days = hours / 24;

    hours %= 24;
    minutes %= 60;
    seconds %= 60;

    std::cout << "Your PC has been running for: "
        << days << " days, "
        << hours << " hours, "
        << minutes << " minutes, "
        << seconds << " seconds." << std::endl;
    system("pause");
    return 0;
}
```
⚡ Features

    Displays your PC uptime in a readable format: days, hours, minutes, seconds.

    Uses the Windows API GetTickCount64() for accurate uptime.

🛠️ Build

The project is in C++ and can be compiled with Visual Studio or g++ (MinGW).

Example with g++:
```
g++ -std=c++17 -o PcCount.exe main.cpp
```
🚀 Usage

    Run the executable:

PcCount.exe

    The console will show how long your PC has been running.

📜 License

MIT License – free to use, modify, and share.
