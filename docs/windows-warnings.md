# Getting past Windows warnings

MythosLoader is not code-signed yet. Code signing is how Windows recognises a publisher, so until it is in place
Windows treats every new release as "unknown" and may warn about it or block it. This page walks through each
warning you may see, what it means, and how to get MythosLoader running safely.

**The safe order of things:** download only from the
[official Releases page](https://github.com/d2r-mythos/MythosLoader/releases/latest), check the checksum (step 1),
and only then tell Windows to trust the file. Never follow these steps for a MythosLoader download from anywhere else.

---

## Quick version

1. Download `MythosLoader-<version>-win-x64.zip` and `SHA256SUMS.txt` from the
   [Releases page](https://github.com/d2r-mythos/MythosLoader/releases/latest).
2. Check the checksum (below).
3. Right-click the zip → **Properties** → tick **Unblock** → **OK**.
4. Extract the zip and run `MythosLoader.exe`.
5. If a blue **"Windows protected your PC"** window still appears: **More info** → **Run anyway**.

If Windows says **"Smart App Control blocked an app"**, see [Smart App Control](#5-smart-app-control-blocked-an-app)
— that one works differently.

---

## 1. Check the download

Every release has a `SHA256SUMS.txt` file listing the exact fingerprint of the zip. If your fingerprint matches,
the file is exactly the one we published.

1. Open the folder with the download (usually **Downloads**).
2. Click the address bar, type `powershell`, press **Enter**. A PowerShell window opens in that folder.
3. Run (use the real file name):

   ```powershell
   Get-FileHash .\MythosLoader-1.2.3-win-x64.zip -Algorithm SHA256
   ```

4. Compare the long `Hash` value with the line in `SHA256SUMS.txt` (upper or lower case does not matter).
   **Different? Delete the file and download it again.** Do not run it.

## 2. Your browser warns about the download

Browsers sometimes hold back files that few people have downloaded yet.

- **Microsoft Edge** — "*MythosLoader… isn't commonly downloaded*": hover the download, click **…** → **Keep** →
  **Show more** → **Keep anyway**.
- **Google Chrome** — "*… may be dangerous*" or a blocked download: open the downloads list (**Ctrl+J**) and click
  **Keep** / **Download unverified file**.
- **Firefox** — "*This file is not commonly downloaded*": open the downloads list and choose **Allow download**.

Then check the file as in step 1.

## 3. Unblock the zip before extracting (prevents the SmartScreen window)

Windows marks every downloaded file as "from the internet", and the built-in zip extractor copies that mark onto
everything it extracts. That mark is what makes SmartScreen step in. Removing it from the zip **before** extracting
means `MythosLoader.exe` starts without the warning.

**With the mouse**

1. Right-click the zip → **Properties**.
2. On the **General** tab, at the bottom next to *Security: This file came from another computer…*, tick
   **Unblock**.
3. Click **OK**, then extract the zip.

No *Unblock* box? The file is already unblocked, or Windows did not mark it. Carry on.

**With PowerShell** (same result)

```powershell
Unblock-File -Path "$env:USERPROFILE\Downloads\MythosLoader-1.2.3-win-x64.zip"
```

Already extracted? Unblock the files in the folder instead:

```powershell
Get-ChildItem "C:\path\to\MythosLoader" -Recurse | Unblock-File
```

## 4. "Windows protected your PC" (SmartScreen)

A blue window saying *Microsoft Defender SmartScreen prevented an unrecognized app from starting*.

1. Click **More info**.
2. Check that the app is `MythosLoader.exe`, then click **Run anyway**.

Windows remembers this for this copy of the file. You only see it again for a new release downloaded through a
browser.

**Updates do not trigger this.** When MythosLoader updates itself with its **Update** button, the new version is
not marked as downloaded from the internet, so it starts without any SmartScreen window.

## 5. "Smart App Control blocked an app"

Smart App Control is a stricter Windows 11 feature. When it is **on**, it blocks every program that is not
code-signed or already known to Microsoft, and it offers **no "Run anyway"** button. Unblocking the file
(step 3) does not change that.

**Check whether it is on:** **Start** → *Windows Security* → **App & browser control** → **Smart App Control
settings**. It shows **On**, **Evaluation** or **Off**.

- **Evaluation:** Windows is still deciding whether to switch it on. MythosLoader may run today and be blocked
  later if Windows switches it on.
- **On:** MythosLoader cannot run on this PC while Smart App Control is on, because it is not code-signed yet.
  The only way to run it today is to **turn Smart App Control off** (same settings page → **Off**). Think about
  this first: on most Windows versions you cannot turn it back on later without resetting or reinstalling Windows.
  Your normal antivirus (Microsoft Defender) keeps working when it is off. Only do this on a PC you are comfortable
  running without it.

There is no way to make an exception for a single program while Smart App Control is on. That is by design, and
we will not suggest tricks to get around it.

## 6. Microsoft Defender or another antivirus removes the file

A multi-launcher has to close the game's "already running" check inside the game process. A few antivirus
products find that unusual and flag it. MythosLoader does nothing else of the kind: no injection, no memory
reading, no input automation.

1. Check the file against `SHA256SUMS.txt` first (step 1). If it does not match, do not restore it.
2. **Microsoft Defender:** **Windows Security** → **Virus & threat protection** → **Protection history** → the
   MythosLoader entry → **Actions** → **Restore** (or **Allow on device**).
3. Report it as a false positive so other users are not affected:
   [Microsoft's file submission page](https://www.microsoft.com/en-us/wdsi/filesubmission) (choose *Incorrectly
   detected as malware*), and tell us on [Discord](https://discord.com/invite/d2rmythos) which version and which
   antivirus.

## Still stuck?

Ask on the [D2R Mythos Discord](https://discord.com/invite/d2rmythos). Say which message you see (a screenshot
helps), which Windows version you have, and what *Smart App Control settings* shows.
