# ZMK Firmware: Personal fork

[ZMK Firmware](https://zmk.dev/) is an open source ([MIT](LICENSE)) keyboard firmware built on the [Zephyr™ Project](https://www.zephyrproject.org/) Real Time Operating System (RTOS). ZMK's goal is to provide a modern, wireless, and powerful firmware free of licensing issues.

Check out the website to learn more: https://zmk.dev/.

You can also come join our [ZMK Discord Server](https://zmk.dev/community/discord/invite).
Below is a list of features
currently included in the `main` branch _on top of_ the official ZMK master branch.

- **mouse** (PR [#778](https://github.com/zmkfirmware/zmk/pull/778)) - official PR + ftc's changes + [fixes needed for Zephyr 3.2](https://github.com/urob/zmk/tree/mouse-3.2) + safeguads + always use hog device
- **swapper** (PR [#1366](https://github.com/zmkfirmware/zmk/pull/1366)) - official PR + fixes needed for Zephyr 3.2
- **global-quick-tap-ms** (PR [#1387](https://github.com/zmkfirmware/zmk/pull/1387)) - official PR
- **smart-word** (PR [#1451](https://github.com/zmkfirmware/zmk/pull/1451)) - official PR, updated to Zephyr-3.2
- **fix-key-repeat** - fix [key-repeat rolling issue](https://github.com/zmkfirmware/zmk/issues/1207)
  by Andrew Rae
- **on-release-for-tap-preferred** - [on-release feature for tap-preferred](https://github.com/celejewski/zmk/commit/d7a8482712d87963e59b74238667346221199293) by Andrzej
- **adv360pro** - driver + [alternate matrix transform](https://github.com/urob/adv360-demo-config#alternate-matrix-transform)
- **zen-tweaks** - [display & battery improvements](https://github.com/caksoylar/zmk/tree/caksoylar/zen-v1%2Bv2) by Cem Aksoylar

In order to use this branch with Github Actions, replace the contents of `west.yml` in
your `zmk-config/config` directory with the following contents:

```
manifest:
  remotes:
    - name: urob
      url-base: https://github.com/urob
  projects:
    - name: zmk
      remote: urob
      revision: main
      import: app/west.yml
  self:
    path: config
```
