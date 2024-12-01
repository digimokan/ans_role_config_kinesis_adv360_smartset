# ans_role_config_kinesis_adv360_smartset

Configure an attached Kinesis Advantage360 keyboard with custom keymaps.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_kinesis_adv360_smartset.svg?label=release)](https://github.com/digimokan/ans_role_config_kinesis_adv360_smartset/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Requirements](#requirements)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Programming Notes](#programming-notes)
    * [Default Key Locations](#default-key-locations)
    * [Types Of Keymaps](#types-of-keymaps)
    * [Commonly Remapped Key Names](#commonly-remapped-key-names)
* [Contributing](#contributing)

## Purpose

* Provide a [utility script](../templates/utility_script.j2) to configure an
  attached [Kinesis Advantage360 Keyboard](https://kinesis-ergo.com/support/kb360/)
  keyboard with custom keymaps.

## Supported Operating Systems

* Ubuntu
* Arch Linux
* FreeBSD

## Requirements

* The Advantage360 keyboard is a non-"pro" variant, which uses SmartSet
  programming, not the newer ZMK programming.
* The Advantage360 keyboard is attached to the system, via USB or Bluetooth.
* The keyboard's v-Drive has been exposed as a USB device, via pressing the
  _Smartset_ + _v-Drive_ keys.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_kinesis_adv360_smartset
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Configure an attached Kinesis Advantage360 keyboard with custom keymaps"
         ansible.builtin.include_role:
           name: ans_role_config_kinesis_adv360_smartset
   ```

## Role Options

Vars defined by this role, exported with `public: true`, for use in other roles:

  * [export](../defaults/main/export/commands.yml)

## Programming Notes

### Default Key Locations

The following default keys must be specified on the left side of all remaps.

![Default Keys](./readme/default_keys.png)

### Types Of Keymaps

Simple 1:1 key remap:

```
[hk1]>[home]
```

Macro remap of left shift key to produce an underscore:

```
{lshf}>{-rshf}{hyph}{+rshf}
```

### Commonly Remapped Key Names

* `hyph` : - and _
* `eql`  : = and +
* `obrk` : [ and {
* `cbrk` : ] and }
* `comm` : , and <
* `perd` : . and >
* `fsls` : / and ?
* `bsls` : \ and |
* `apos` : ‘ and “
* `scol` : ; and :
* `grav` : Grave and ~
* `caps` : Caps Lock
* `tab`  : Tab
* `spc`  : Spacebar
* `ent`  : Return
* `del`  : Delete
* `esc`  : Escape
* `bspc` : Delete
* `home` : Home
* `end`  : End
* `pgup` : Page Up
* `pgdn` : Page Down
* `left` : Left Arrow
* `down` : Down Arrow
* `paus` : Pause
* `ins`  : Insert
* `sclk` : Scroll Lock
* `prnt` : Print Screen
* `rght` : Right Arrow
* `up`   : Up Arrow
* `nmlk` : Num Lock
* `mute` : Mute
* `vol+` : Volume Up
* `vol-` : Volume Down
* `plpa` : Play / Pause
* `lshf` : Left Shift
* `rshf` : Right Shift
* `lctr` : Left Control
* `rctr` : Right Control
* `lalt` : Left Alt
* `ralt` : Right Alt
* `lwin` : Left Gui
* `rwin` : Right Gui
* `keys` : Keypad Layer Shift
* `keyt` : Keypad Layer Toggle
* `fn1s` : FN1 Layer Shift
* `fn1t` : FN1 Layer Toggle
* `fn2s` : FN2 Layer Shift
* `fn2t` : FN2 Layer Toggle
* `fn3s` : FN3 Layer Shift
* `fn3t` : FN3 Layer Toggle
* `hk1`  : Hotkey 1
* `hk2`  : Hotkey 2
* `hk3`  : Hotkey 3
* `hk4`  : Hotkey 4

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_kinesis_adv360_smartset/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

