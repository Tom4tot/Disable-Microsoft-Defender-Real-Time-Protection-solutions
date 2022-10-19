# Microsoft Defender Real-Time Protection solutions (Windows 11)
### Purpose of this page  
- I found out that this topic is more complex than I first thought. It's hard to find up-to-date information on the Internet and pros/cons of each method.
- Solutions will be ranked from best to worst, in my opinion.
### Prerequisites and context
No matter which approach you choose (except the Windows Security one, which is by far the worst since your setting won't stick), **you have to** disable Tamper Protection from the Windows Security UI: `Windows Security → Virus and threat protection → Virus and threat protection settings → Tamper Protection → off`.  
If you don't do that, Windows will block any third-party change, including ones from official components such as CMD or PowerShell.  
Tamper Protection has to be disable from settings, it can't be disabled from anywhere else. The change simply won't stick.

## Method 1: Group Policy Editor (recommended)
- How-to: `Computer Configuration > Administrative Templates > Windows Components > Microsoft Defender Antivirus > Real-time protection → Turn off real-time protection (enabled)`
- Pros:
  - Native feature
  - Easy to turns on and off
  - Should survive Windows Updates
- Cons 
  -  Doesn't work with Home edition of Windows (without any hack)
  -  Not very convenient to turn on and off

## Method 2: Task Scheduler - [Microsoft Defender Real-Time Protection stop](https://github.com/duttyend/Microsoft-Defender-RTP-stop) (recommended)
- How-to: see instructions
- Pros: 
  - Only uses official Windows features and components (i.e. Task Scheduler and PowerShell).
  - Works natively on Windows Home edition
  - Extremely easy to turn on and off
  - Should survive Windows Updates
- Cons
  - RTP can potentially work for a few seconds a day

## Method 3: Regedit (not recommended)
- Cons
  - It can easily become oudated after an updates
  - It could lead to instabilities

## Method 4: Windows Security UI (not recommended)
- Pros
  -  You can keep Tamper Protection enabled
- Cons 
  - Your change won't stick after a certain period of time (the triggers are not documented by Microsoft) or after a reboot

## Method 5: third-party softwares (not recommended)
- Cons
  - It can easily become oudated after an updates
  - You usually don't know what the program is actually doing
  - It can conflict with Windows native features and lead to instabilities
  - Lots of tools completely break Microsoft Defender and it becomes hard to recover it

