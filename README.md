# 4-Axis Fusion 360 Post Processor

This repository contains a **Fusion 360 Post Processor** specifically designed for 4-axis laser-based machining. It enables tailored G-code output for controlling machines with rotary motion (A/B/C axis) alongside the standard X, Y, and Z axes. Key features include flexible property configuration, multi-axis movement handling, tool compensation options, and laser PWM output.

## Features

- **4-Axis Control**: Supports generating G-code for an additional rotary axis (A, B, or C) through user-configurable properties.
- **Laser PWM Integration**: Includes properties to specify laser power, so you can easily set PWM power within your G-code.
- **Machine Configuration**: Defines multiple user-editable settings such as workspace offsets, coolant options, and safe retract methods.
- **Sequence Numbers**: Offers optional sequence numbering per line, per tool change, or no sequence numbers at all.
- **Tool & Coolant Management**: Manage tool information, coolant activation, and advanced settings (SmartCool, Multi-Cool, etc.).
- **Workspace Offsets**: Allows customized G-code origin offsets via X, Y, Z workspace offsets.
- **Safe Retracts**: Choose different methods for retracting (G28, G30, clearance height, or G53) for safe axis repositioning.

## Getting Started

1. **Download or Clone** this repository to your local machine.
2. **Import the Post Processor** into Fusion 360:
   - Open **Fusion 360**.
   - Go to **Manufacture** workspace.
   - Under **Manage**, select **Personal Post Library** (or **Cloud Post Library** if you prefer).
   - Add the `.cps` or `.js` post file from this repository.
3. **Configure the Post**:
   - In your **CAM Setup**, select **Coela 4-Axis** as the post processor.
   - Adjust **Post Properties** in the Fusion 360 Post dialog to match your machine and preferences (e.g., axis of rotation, safe position methods, tool offset ranges, laser power settings, etc.).
4. **Generate Your G-code**:
   - In **Fusion 360**, generate toolpaths as usual.
   - Post-process using the **Coela 4-Axis** post to produce `.gcode` files tailored to your machine’s rotary axis and laser requirements.

## Usage Notes

- **Laser PWM Control**: This post includes lines to enable/disable the laser and set the PWM power (via 'laserPWMPower'). Ensure your machine’s firmware/controller supports these commands.
- **Safe Retract Method**: By default, the post uses 'G30' or 'G28' for safe retracts, but this can be changed in the post properties.
- **4-Axis Rotation**: The property 'rotaryTableAxis' must be set to 'X', 'Y', or 'Z' (with normal or reversed direction) to output 4-axis moves. If 'none' is selected, no rotary moves will be generated.
- **Workspace Offsets**: If needed, you can shift the G-code origin by specifying 'workSpaceOffsetX', 'workSpaceOffsetY', and 'workSpaceOffsetZ'.
- **Multiple Settings**: Explore additional properties for tool numbering, dwell times, feed formats, and coolant usage.

This post processor file is placed in your Fusion 360 Posts directory.

## Contributing

Feel free to open issues or submit pull requests for improvements:
- **Bug Reports**: Encountered an error? Let us know with details and steps to reproduce.
- **Feature Requests**: Suggest new features or property options.
- **Code Contributions**: Fork the repository, make changes, and open a PR.

## License

This project is provided as-is without a specific license. If you modify the code, please retain credit.
