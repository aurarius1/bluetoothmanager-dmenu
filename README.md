# bluetoothmanager-dmenu


# Requirements
* pydbus
* bluez
* bluez-utils
* optional: [bluetooth manager](https://wiki.archlinux.org/title/Bluetooth)

The script is tested on Arch, with python-pydbus.

# Plans
This is (and probably will always be) work in progress.

I plan to add support for BLE (Airpods etc.) battery capabilities.


# Configuration
The `config.ini.example(default: blueman-manage1r)` file shows the default values bluetoothmanager-dmenu uses. If you are happy with the default configuration values, you do not need to create a `config.ini` file at all. The config path `bluetoothmanager-dmenu` checks is `$HOME/.config/bluetoothmanager-dmenu`. If you want to change the path you can do this by using the `--config / -c` arguments when launching.
| Section              | Key                | Default                | Explanation                                            |
|----------------------|--------------------|------------------------|--------------------------------------------------|
| `[dmenu]`            | `command`          | `walker`               | The launcher you want to use                                                 |
|                      | `arguments`        | `-n -d -k`             | The arguments your launcher needs to run in dmenu mode (+ configuration flags)                   |
|                      | `prompt`           | `-p`                   | The flag to set the value for the prompt                                                 |
|                      | `connected_symbol` | ``                   | The symbol shown next to each connected (not paired) device                                                 |
|                      | `battery_symbol`     | `󰥈`                     | The symbol shown next to the battery level (if the device exposes any)                      |
| `[manager]`         | `enabled`      | `false` | If you want to be able to launch a dedicated bluetooth manager from the dmenu                                                |
|                      | `app`           | `blueman-manager`            | The dedicated bluetooth manager that will be launched                                                |
|                       | `gui`         | `true`        | If it is a gui based manager or not                       |  
|                       | `terminal`    | `kitty`       | Which terminal to use if `app` is not gui based           |

# Attribution
Heavily inspired by: 

* [networkmanager-dmenu](https://github.com/firecat53/networkmanager-dmenu) (code, structure, naming etc.)
* [dmenu-bluetooth](https://github.com/Layerex/dmenu-bluetooth) (idea)