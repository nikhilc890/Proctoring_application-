# CyberProctor Secure Agent

CyberProctor is a lightweight but strict desktop proctoring agent deployed as a standalone Python executable. Designed to maintain the integrity of online interviews, this agent forcefully locks down the candidate's environment, prevents screen-sharing, stops cheating tools, and ensures focus is strictly on the meeting.

## Features

- **Secure Kiosk Mode**: Locks the candidate into a full-screen, top-most interface.
- **Hardware Enforcement**: Detects multiple displays at startup and during the interview. Forces the user to unplug external monitors before proceeding.
- **Microphone & Camera Diagnostics**: Built-in hardware check UI prior to launching interviews.
- **Blacklisted Application Terminator**: Actively scans and immediately kills unauthorized applications such as:
  - **Parakeet AI** & other AI-assisted interview tools
  - Screen recorders (OBS Studio, Camtasia)
  - Remote desktop software (AnyDesk, TeamViewer)
  - Messaging apps (Discord, Telegram, Skype)
- **Keyboard Hooking**: Disables system shortcuts like `Alt+Tab`, `Windows Key`, `Ctrl+Esc`, etc.
- **Secure Meeting Launch**: Spawns Zoom or Google Meet inside an isolated container so the browser cannot be manipulated (no URL bar, restricted extensions). 
- **Anti-Debugger & Proxy Check**: Ensures the integrity of the network and memory space.


## How to Use

1. Double click `proctor_agent.exe`.
2. Allow Administrative privileges (UAC prompt).
3. Connect precisely **one** display. If an external monitor is plugged in, the meeting launch buttons will be locked.
4. Perform the **Device Check** to ensure Camera and Microphone are functioning.
5. Choose **Launch Zoom** or **Launch Google Meet**.
6. A Secure Browser Window will launch with the meeting interface and a red `Close` button overlaid over the secured environment.

**Security Enforcements during runtime:**
- Any attempt to plug in a second monitor will immediately terminate the interview browser.
- Opening software like Parakeet AI will be instantly detected and task-killed by the heartbeat scanner.

## Disclaimer

This software restricts input, intercepts system shortcuts, and forcefully terminates processes. It is explicitly meant for authorized candidate proctoring sessions.
