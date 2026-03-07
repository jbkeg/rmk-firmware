# V1 Target Inventory (Frozen from ZMK build.yaml)

Source: `d:\zmk-config\build.yaml` (frozen at migration kickoff).

Total targets: 50

| Artifact | Board | Shield | Snippet | CMake Args |
|---|---|---|---|---|
| `totem_left` | `seeeduino_xiao_ble` | `totem_left` | `common-config studio-rpc-usb-uart` | `` |
| `totem_right` | `seeeduino_xiao_ble` | `totem_right` | `` | `` |
| `totem_left_w_dongle` | `seeeduino_xiao_ble` | `totem_left_w_dongle` | `` | `` |
| `totem_dongle` | `nice_nano_v2` | `totem_dongle` | `common-config studio-rpc-usb-uart` | `` |
| `totem_zdd_dongle` | `nice_nano_v2` | `totem_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"TOTEM\ ZDD\"` |
| `urchin_left` | `nice_nano_v2` | `urchin_left nice_view_adapter nice_view_gem` | `common-config studio-rpc-usb-uart` | `` |
| `urchin_right` | `nice_nano_v2` | `urchin_right nice_view_adapter nice_view_gem` | `` | `` |
| `urchin_left_w_dongle` | `nice_nano_v2` | `urchin_left_w_dongle nice_view_adapter nice_view_gem` | `` | `` |
| `urchin_dongle` | `nice_nano_v2` | `urchin_dongle` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_DISPLAY=n -DCONFIG_DISPLAY=n -DCONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=n` |
| `urchin_zdd_dongle` | `nice_nano_v2` | `urchin_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Urchin\ ZDD\"` |
| `corne_left` | `nice_nano_v2` | `corne_left nice_view_adapter nice_view` | `common-config studio-rpc-usb-uart` | `` |
| `corne_right` | `nice_nano_v2` | `corne_right nice_view_adapter nice_view` | `` | `` |
| `corne_left_w_dongle` | `nice_nano_v2` | `corne_left nice_view_adapter nice_view` | `` | `-DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n` |
| `corne_dongle` | `nice_nano_v2` | `corne_dongle` | `common-config studio-rpc-usb-uart` | `` |
| `corne_zdd_dongle` | `nice_nano_v2` | `corne_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Corne\ ZDD\"` |
| `eyelash_corne_left` | `eyelash_corne_left` | `nice_view` | `common-config studio-rpc-usb-uart` | `` |
| `eyelash_corne_right` | `eyelash_corne_right` | `nice_view` | `` | `` |
| `eyelash_corne_left_w_dongle` | `eyelash_corne_left` | `nice_view` | `` | `-DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n` |
| `eyelash_corne_dongle` | `nice_nano_v2` | `eyelash_corne_dongle` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_DISPLAY=n -DCONFIG_DISPLAY=n -DCONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=n` |
| `eyelash_corne_zdd_dongle` | `nice_nano_v2` | `eyelash_corne_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"EyelashCorneZDD\"` |
| `sofle_left` | `nice_nano_v2` | `sofle_left nice_view_adapter nice_view` | `common-config sofle-sides-config studio-rpc-usb-uart` | `` |
| `sofle_right` | `nice_nano_v2` | `sofle_right nice_view_adapter nice_view` | `sofle-sides-config` | `` |
| `sofle_left_w_dongle` | `nice_nano_v2` | `sofle_left nice_view_adapter nice_view` | `sofle-sides-config` | `-DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n` |
| `sofle_dongle` | `nice_nano_v2` | `sofle_dongle` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_DISPLAY=n -DCONFIG_DISPLAY=n -DCONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=n` |
| `sofle_zdd_dongle` | `nice_nano_v2` | `sofle_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Sofle\ ZDD\"` |
| `eyelash_sofle_left` | `eyelash_sofle_left` | `nice_view` | `common-config studio-rpc-usb-uart` | `` |
| `eyelash_sofle_right` | `eyelash_sofle_right` | `nice_view` | `` | `` |
| `eyelash_sofle_left_w_dongle` | `eyelash_sofle_left` | `nice_view` | `` | `-DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n` |
| `eyelash_sofle_dongle` | `nice_nano_v2` | `eyelash_sofle_dongle` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_DISPLAY=n -DCONFIG_DISPLAY=n -DCONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=n` |
| `eyelash_sofle_zdd_dongle` | `nice_nano_v2` | `eyelash_sofle_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"EyelashSofleZDD\"` |
| `delta_omega_left` | `seeeduino_xiao_ble` | `delta_omega_left` | `common-config studio-rpc-usb-uart` | `` |
| `delta_omega_right` | `seeeduino_xiao_ble` | `delta_omega_right` | `` | `` |
| `delta_omega_left_w_dongle` | `seeeduino_xiao_ble` | `delta_omega_left_w_dongle` | `` | `` |
| `delta_omega_dongle` | `nice_nano_v2` | `delta_omega_dongle` | `common-config studio-rpc-usb-uart` | `` |
| `delta_omega_zdd_dongle` | `nice_nano_v2` | `delta_omega_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Delta\ Omega\ ZDD\"` |
| `cornix_left` | `cornix_left` | `` | `common-config studio-rpc-usb-uart` | `` |
| `cornix_right` | `cornix_right` | `` | `` | `` |
| `cornix_left_w_dongle` | `cornix_left` | `` | `` | `-DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=n` |
| `cornix_dongle` | `nice_nano_v2` | `cornix_dongle` | `common-config studio-rpc-usb-uart` | `` |
| `cornix_zdd_dongle` | `nice_nano_v2` | `cornix_dongle zdd_adapter dongle_display` | `common-config studio-rpc-usb-uart` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Cornix\ ZDD\"` |
| `reset_nice_nano_v2` | `nice_nano_v2` | `settings_reset` | `` | `` |
| `reset_seeeduino_xiao_ble` | `seeeduino_xiao_ble` | `settings_reset` | `` | `` |
| `totem_prospector_dongle` | `seeeduino_xiao_ble` | `totem_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"TOTEM\ PRSP\"` |
| `urchin_prospector_dongle` | `seeeduino_xiao_ble` | `urchin_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Urchin\ PRSP\"` |
| `corne_prospector_dongle` | `seeeduino_xiao_ble` | `corne_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Corne\ PRSP\"` |
| `eyelash_corne_prospector_dongle` | `seeeduino_xiao_ble` | `eyelash_corne_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"ELCornePRSP\"` |
| `sofle_prospector_dongle` | `seeeduino_xiao_ble` | `sofle_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Sofle\ PRSP\"` |
| `eyelash_sofle_prospector_dongle` | `seeeduino_xiao_ble` | `eyelash_sofle_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"ELSoflePRSP\"` |
| `delta_omega_prospector_dongle` | `seeeduino_xiao_ble` | `delta_omega_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"DeltaOmegaPRSP\"` |
| `cornix_prospector_dongle` | `seeeduino_xiao_ble` | `cornix_dongle prospector_adapter` | `common-config studio-rpc-usb-uart prospector-config` | `-DCONFIG_ZMK_KEYBOARD_NAME=\"Cornix\ PRSP\"` |

## Notes
- This file is intentionally generated/frozen for migration traceability.
- Artifact names are compatibility constraints for RMK v1.
