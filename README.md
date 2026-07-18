# ncSenderOS for Sienci gControl Panel

A purpose-built Debian-based operating system that turns the Sienci
**gControl Panel** into a dedicated **ncSenderPro** kiosk — boots straight to
ncSenderPro in full-screen touch mode, no desktop, no distractions.

> [!CAUTION]
> **This will erase everything on the gControl Panel's internal SSD.**
> The Windows installation, the gSender application, all saved jobs, all
> configuration, and your machine files stored on the panel — all of it will
> be permanently wiped and replaced with ncSenderOS.
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
- **ncSender Pro** is the paid version — <https://www.franciscreation.com/ncsender-pro>

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

## What ncSenderOS does

- Boots the panel directly into **ncSenderPro** in kiosk mode (no login screen,
  no desktop, no browser)
- Uses the full SSD for the OS + your files (single ext4 partition)
- WiFi and Ethernet both work out of the box via NetworkManager
- Touchscreen is auto-configured
- Root password is `ncsender` (SSH is available if you need it for advanced
  configuration; leaving it at default on a workshop network is fine)
- Powers on straight into your controller UI every time — no clicks needed

---

## Install instructions

You will need:

- The gControl Panel
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
