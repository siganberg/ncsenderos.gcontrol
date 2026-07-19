# ncSenderOS for Sienci gControl Panel

A purpose-built Debian-based operating system that turns the Sienci
**gControl Panel** into a dedicated **ncSenderPro** kiosk — boots straight to
ncSenderPro in full-screen touch mode, no desktop, no distractions.

Think of it as turning the gControl Panel into a **dedicated CNC control PC**,
similar in spirit to a **Masso Touch Panel** or a **Centroid AcornSix Touch
Screen** — a single-purpose appliance for running your machine, not a general
Windows PC.

> [!IMPORTANT]
> **This is a ncSenderPro appliance.** The OS bundles ncSenderPro and
> requires a **ncSenderPro license** to activate. If you don't already own
> ncSenderPro, get it here first: <https://www.franciscreation.com/ncsenderpro>.
> If you're using the free community version of ncSender, this OS isn't for
> you — try the community app on your existing Windows setup instead.

> [!CAUTION]
> **This will erase everything on the gControl Panel's internal SSD** — the
> Windows installation, the gSender application, all saved jobs, all
> configuration, and every file stored on the panel. All of it will be
> permanently wiped and replaced with ncSenderOS.
>
> **Back up anything you might want before you start.** Copy any G-code files,
> job history, macros, tool tables, calibration data, saved settings, license
> keys, and any personal files off the panel to an external drive or another
> computer. Once the installer wipes the SSD, none of it is recoverable — not
> by me, not by Sienci Labs, not by any recovery tool.
>
> Only install this if you have decided you are **permanently switching from
> gSender to ncSenderPro**. Please read the [Before you install](#before-you-install)
> section below in full.

---

## Before you install

**Please try the free community version of ncSender on your existing gControl
Panel first — before wiping anything.** ncSender (community) is a Windows/macOS/
Linux desktop application; you can install it side-by-side with gSender on the
panel and see whether the workflow, UI, and machine control fit how you work,
without touching your installation.

- **Download ncSender (community)**: <https://github.com/siganberg/ncSender/releases>
- **ncSender Pro** is the paid version — <https://www.franciscreation.com/ncsenderpro>

Confirm ncSenderPro is right for you *before* going any further. Going back to
gSender/Windows after installing ncSenderOS is **not** a simple undo:

> [!WARNING]
> **Reverting to the factory Windows + gSender setup requires:**
>
> 1. **A separate Windows installation USB** — you will need to reflash Windows
>    from scratch. Sienci does not ship the panel with a recovery partition
>    after this install.
> 2. **Your Windows license key** — the original Windows license that came
>    with the panel. Have this in hand *before* you install ncSenderOS.
>    Without it, the reinstalled Windows will not activate.
> 3. **Re-downloading and re-installing gSender**, machine settings, macros,
>    tools, and any files you had saved locally.
>
> Sienci Labs cannot recover Windows or gSender for you after this. This is a
> one-way door unless you are prepared to redo the factory install yourself.

If any of that gives you pause — install ncSender (community) on your existing
Windows first and try it there. You lose nothing by doing so.

---

## Disclaimer

**Use this software entirely at your own risk.**

- I am an independent developer sharing this project as-is, in the hope that
  it's useful. I am **not** affiliated with Sienci Labs, Masso, Centroid,
  Microsoft, or any hardware vendor.
- I am **not responsible** for any loss of data, loss of your Windows
  installation, loss of your Windows license, loss of gSender configuration,
  bricked hardware, voided warranties, missed deadlines, unfinished jobs,
  ruined stock, damaged tooling, machine crashes, workshop injuries, or any
  other direct or indirect damages resulting from installing or using this
  software.
- You are responsible for **backing up everything important** before you
  install, and for confirming that ncSenderPro is what you want on this
  hardware **before** you commit.
- This software is provided **"AS IS", without warranty of any kind**,
  express or implied, including but not limited to the warranties of
  merchantability, fitness for a particular purpose, and noninfringement.
  In no event shall the author be liable for any claim, damages, or other
  liability, whether in an action of contract, tort, or otherwise, arising
  from, out of, or in connection with the software or the use or other
  dealings in the software.

By downloading, flashing, and installing this image, you acknowledge that
you have read and accept these terms, and that all consequences of the
install — good or bad — are yours to own.

If you are not comfortable with any of the above, **do not install it**.
Use the free community version of ncSender on your existing Windows setup
instead — same UI, same core features, zero risk to your panel.

---

## Why choose ncSenderOS over the stock Windows setup

The gControl Panel with stock Windows + gSender is a general-purpose PC that
happens to be running a CNC controller. ncSenderOS turns it into a
**dedicated CNC control appliance** — every design decision is made in favor
of the machine on your workbench, not the operating system.

### Real screen space, all of it

- **Full-screen kiosk** — no desktop, no taskbar, no window title bar, no
  Windows notifications sliding in mid-job. The full display is your
  controller UI.
- **Touch-friendly virtual keyboard** — pops up when you need to type
  (filenames, coordinates, WiFi passwords), goes away when you don't.
  Sized and positioned for touch, not laptop typing.

### Rotate the panel any way you want

- **Full screen-rotation support** — landscape, portrait (either side), or
  upside-down. Configured at the OS level, so the touchscreen coordinates
  stay correct after rotation (no more calibrating an X where you touched Y).
- Mount the panel over your machine, next to it, or on a swing arm — the
  OS adapts to how you have it physically installed.

### Boot straight to work

- **Under 30 seconds** from power button to ncSenderPro ready to jog — no
  login, no lockscreen, no desktop, no "Getting Windows ready" screens, no
  "please wait while we update your drivers".
- No user accounts to manage, no password prompts between the shop floor
  and the controller UI.

### No interruptions

- **No Windows Update rebooting your machine mid-job.** No background
  scanning, no telemetry, no Cortana, no Edge auto-updates, no OneDrive
  syncing, no antivirus fighting for CPU while you're cutting a pocket.
- **Sleep, suspend, and hibernate are disabled** — the panel stays on and
  responsive as long as it has power. Long jobs won't wake up to find the
  panel dozing.
- **WiFi doesn't power itself down mid-job** — no dropped connections
  during long jobs or while jogging manually.
- **Nothing else running in the background.** When you tap Jog, the
  machine moves — no waiting for Windows to finish "one moment please".

### Reliable connection to your CNC controller

- Your machine's controller board just shows up and stays connected. No
  random disconnects mid-job, no "the port disappeared again" mysteries
  after a Windows update decides to change something behind your back.
- Works with the common controller boards out of the box (grblHAL, FluidNC,
  Arduino-based GRBL, Longboards, and similar) — no driver hunting, no
  "please install this to use your device" pop-ups.

### Feels snappy, stays snappy

- The panel feels fast the moment it boots — menus open instantly, jogging
  responds without lag, the G-code preview scrolls smoothly. Nothing else
  is fighting for CPU or memory.
- It behaves the same on day 1000 as it did on day 1. Nothing slowly
  accumulates in the background, nothing needs "cleaning up" every few
  months, nothing gets slower over time.
- Because the panel isn't constantly writing junk to disk in the
  background (indexing, updates, temp files), the SSD lasts longer.

### Practical extras

- **Plug in a USB drive with G-code — it just shows up** in ncSenderPro's
  file picker. No pop-ups, no dialogs, no "click here to open this drive"
  windows in the way.
- **Copy files to the panel over your workshop network** from your
  desktop or laptop — no shuffling USB sticks back and forth.
- **Ethernet or WiFi** — both work out of the box, no drivers to install.
- **The full internal drive is available** for the OS and your files.

### If something goes wrong, recovery is easy

- If the software ever gets into a bad state, just **reflash the same USB**
  and you're back to a known-good, working panel in about 10 minutes. No
  hours of Windows repair tools, no "your system needs to be reset" that
  wipes your files, no third-party recovery utilities to hunt down.
- Because your G-code lives on a network share or a USB stick, the panel
  is just the tool that runs the machine — you can swap it, reflash it,
  or replace it without losing your work.

### Nothing extra to worry about

- **No web browser. No email. No Office. No games.** The panel does one
  thing: run ncSenderPro. That means it can't accidentally get infected
  from a wrong click, a phishing email, or a bad USB drive with an
  autorun file — because there's nothing on it to open them.
- No Microsoft account to sign in to, no antivirus subscription to renew,
  no "your license has expired" pop-ups.

### Included with your ncSenderPro license

- **ncSenderOS is for ncSenderPro users.** The ISO bundles ncSenderPro
  and requires an ncSenderPro license to run — same license you'd need
  to run ncSenderPro on Windows. If you're already a ncSenderPro user,
  this OS is provided at no extra cost.
- **No additional subscription, no per-panel fee, no cloud tier.** Your
  existing ncSenderPro license activates on the panel once it boots.
- If you're on the free community version of ncSender, this OS isn't
  the right fit — see the [Before you install](#before-you-install)
  section for how to evaluate ncSenderPro before committing.
- Built on standard Debian (a well-known Linux distribution used by
  millions of people), so nothing here is a mystery black box you're
  stuck depending on. If you ever want to peek under the hood or
  customize it, you can.

---

## Quick facts

- Boots the panel directly into ncSenderPro — no login screen, no desktop
- Uses the whole internal drive for the OS and your files
- WiFi and Ethernet both work out of the box
- Touchscreen is auto-configured with proper rotation
- Root password is `ncsender` (for shop use, this is fine to leave as-is;
  change it via the built-in terminal if you're on an untrusted network)
- Powers on straight into your controller UI every time — no clicks needed

---

## Other Intel N100 / N150 PCs

This is built and tested for the **Sienci gControl Panel**. But the gControl
Panel is an Intel N100 mini PC, and there's a good chance the same image
also works on other Intel **N100 or N150** mini PCs and touch panels — a lot
of the "CNC control panel" boxes on the market use similar hardware inside.

**No guarantees, though.** Different vendors tweak BIOS settings,
touchscreens, WiFi chips, and boot behavior — something that works on the
gControl might not work on yours. The most common trouble spots on
non-gControl hardware are:

- **Touchscreens** — some panels use non-standard controllers that need
  extra drivers
- **WiFi / Bluetooth chips** — some need vendor-specific firmware
- **BIOS boot menus** — Secure Boot, CSM/Legacy settings, boot order

**If you want to try it on other hardware:**

1. Boot from the USB and make it all the way to the installer prompt
   *before* you commit to installing anything. If the display comes up
   wrong, the touchscreen is unresponsive, or the machine won't even boot
   the USB, it's not going to magically work after installing — back out
   at this point.
2. Only proceed with the install if everything up to that prompt looks
   right.
3. **No support is provided for hardware I don't own.** If it works —
   great, please share your experience in the [Discussions](https://github.com/siganberg/ncsenderos.gcontrol/discussions)
   so other people with similar hardware know. If it doesn't work,
   please don't open a bug report expecting a fix.

---

## Install instructions

> By flashing and installing the ISO, you accept the terms in the
> [Disclaimer](#disclaimer). If you haven't read it yet, please scroll up
> and do so before continuing.

You will need:

- The gControl Panel (or a comparable Intel N100/N150 PC — see caveats
  in the [previous section](#other-intel-n100--n150-pcs))
- A **USB flash drive, 4 GB or larger** (its contents will be erased)
- A separate computer to flash the USB — Windows, macOS, or Linux
- A **USB keyboard** temporarily plugged into the panel during install
- Your machine's WiFi credentials (optional — you can also use the RJ45 port)

### 1. Download the ISO

Grab `ncSenderOS-gControl-v<VERSION>.iso` from the
[latest release](https://github.com/siganberg/ncsenderos.gcontrol/releases/latest).

Verify the file matches the SHA-256 published in the release notes.

### 2. Flash the ISO to a USB drive

Use **[balenaEtcher](https://etcher.balena.io/)** — it's free, works on
Windows/macOS/Linux, and is the least error-prone option:

1. Open Etcher
2. **Flash from file** → select the `.iso` you downloaded
3. **Select target** → pick the USB drive (make **absolutely** sure it's the
   right drive — everything on it will be erased)
4. **Flash!** — takes 2–5 minutes

Alternatives: Rufus (Windows), `dd` on macOS/Linux.

### 3. Boot the panel from USB

1. Power off the gControl Panel completely
2. Plug the USB flash drive into any USB port on the panel
3. Plug a USB keyboard into the panel
4. Power on the panel and **immediately** start tapping **`Esc`** (or `F2` /
   `F11` / `Del` — the AMI firmware on the gControl Panel accepts several
   keys) to enter the boot menu
5. In the boot menu, pick the USB drive as the boot device
6. If your panel has **Secure Boot** enabled, you may need to disable it in the
   BIOS setup first (Security → Secure Boot → Disabled)

### 4. Install

- The installer boots automatically — no login required
- Follow the on-screen prompts (there are only a couple of confirmation steps)
- **Final warning: this is the point of no return.** Confirming the install
  will wipe the internal SSD.
- Installation takes ~5–10 minutes
- When it finishes, the panel reboots itself. **Remove the USB drive** before
  the reboot completes.

### 5. First boot

- The panel boots straight into ncSenderPro
- Default root password: `ncsender` (SSH-accessible; change if desired via
  `passwd` at a console)
- Configure WiFi via the ncSenderPro UI, or via `nmtui` / `nmcli` if you drop
  to a console
- Enter your ncSenderPro license key when prompted

That's it — you're on ncSenderOS.

---

## What's in this release

Each release bundles a specific `ncSenderPro` version — the release tag
matches the ncSenderPro version. For example, `v2.0.117` includes
`ncSenderPro v2.0.117`.

To upgrade ncSenderPro after installation, use the built-in Update button in
the ncSenderPro settings — you do not need to reflash the OS.

To move to a newer ncSenderOS base (kernel, system packages), you can either
reflash from a newer release (wipes the SSD again) or, for advanced users,
`apt upgrade` in place. Most users will never need to do this.

---

## Support

- **ncSender / ncSenderPro app issues** — <https://github.com/siganberg/ncSender/issues>
- **ncSenderOS install / boot issues** — <https://github.com/siganberg/ncsenderos.gcontrol/issues>
- **General discussion / Discord** — link in the ncSender manual:
  <https://docs.ncsender.com>

---

## Why this exists

The Sienci gControl Panel is a nice piece of hardware — but out of the box
it's a general-purpose Windows PC running gSender. For hobby users that's
fine, but if you want the panel to behave more like a **Masso Touch Panel**
or a **Centroid AcornSix Touch Screen** — power on, straight to your
controller UI, no desktop, no updates interrupting you mid-job, no browser to
maintain — a dedicated OS is a much better fit.

There isn't a commercial appliance option for people who want to run
ncSenderPro on the gControl Panel that way, so I built one. This project
exists to give ncSender / ncSenderPro users the same "just works" appliance
experience that Masso and Centroid customers get with their touch panels,
without paying for or being locked into either of those ecosystems.

I built and use this on my own machines. It's shared here so other CNC users
who want the same thing don't have to reinvent it.
