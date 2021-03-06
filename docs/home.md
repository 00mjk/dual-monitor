# Documentation / Home

## Getting started
It's recommended (**for quick access**) place the `.dual-monitor` script into the home directory (however you can place it wherever you want):
```bash
$ mv .dual-monitor ~/
```

### Initialization
1. Setup proper **output names** (may be specific for your system). You can see a list of output names by the following command:
    ```bash
    $ xrandr
    ```
2. Provide **executable permissions** for the script:
    ```bash
    $ sudo chmod +x .dual-monitor
    ```
3. Kill processes that occupy the `5900` and `5901` ports.

### How to use
1. **See the docs at first** (the following command prints a manual):
    ```bash
    $ bash .dual-monitor
    ```
2. **Create a mode** (there are default arguments for clarity):
    ```bash
    $ bash .dual-monitor -c -w 1280 -h 1024 -r 60
    ```
3. **Enable the mode**:
    ```bash
    $ bash .dual-monitor -e
    ```
    You should see the output of the `x11vnc` server. Find a string similar as below there to **obtain necessary information** (host and port) to connect a vnc viewer (IP address of the host determines automatically):
    ```
    The VNC desktop is:      192.168.1.103:1
    PORT=5901
    ```
4. **Disable the mode** and close the tracks:
    ```bash
    $ bash .dual-monitor -d -w 1280 -h 1024 -r 60
    ```
    You should use **same arguments as when connecting** to disable necessary mode (in other case it may disable any other mode)!

Use primary commands **in order** mentioned in the documentation **if you don't understand** how `xrandr` works (in other case unexpected behavior may occur).

Don't try to create several same modes (with identical parameters) per a user session! That will not work ;)

## API reference
### Primary commands (without args)
`**-c**` – **create** a mode for a virtual output.

`**-e**` – **enable** a mode of a virtual output.

`**-d**` – **disable** a mode of a virtual output.

### Configuration
> It's recommended to **manually edit this configuration** of the script if you will use it frequently with same parameters which differ from defaults!

`**-h**` – **height** of a virtual screen (default `800`, used with the `-c` and `-d` flags).

`**-p**` – **primary output name** (default `LVDS-1`, used with the `-c` flag).

`**-r**` – **refresh frequency** of a virtual screen (default `60`, used with the `-c` flag).

`**-v**` – **virtual output name** (default `VGA-1`, used with the `-c` and `-d` flags).

`**-w**` – **width** of a virtual screen (default `1280`, used with the `-c` and `-d` flags).