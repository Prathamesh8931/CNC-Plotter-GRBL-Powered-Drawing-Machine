# CNC-Plotter-GRBL-Powered-Drawing-Machine
This machine is a DIY 2D plotter that uses stepper motors to draw vector graphics on paper or light materials. It’s perfect for learning CNC basics, G-code, and GRBL-based automation.

| Component            | Specification / Purpose                     |
| -------------------- | ------------------------------------------- |
| **Controller Board** | Arduino Uno                                 |
| **Motor Driver**     | GRBL Shield (v3 compatible)                 |
| **Motors**           | 2 × NEMA 17 Stepper Motors (X and Y axes)   |
| **Z-Axis**           | SG90 Servo Motor (Pen Up/Down mechanism)    |
| **Power Supply**     | 12V Adapter (sufficient current for motors) |
| **Frame**            | Recycled DVD drives / custom acrylic frame  |
| **Software Stack**   | GRBL Firmware + UGS + Inkscape              |

------------------------------------------------------------------------------------------
Firmware and Software
✅ GRBL Firmware
Uploaded to Arduino Uno

Handles stepper pulse generation, movement planning, and G-code parsing.

✅ Universal G-code Sender (UGS)
Sends G-code to Arduino via USB

Visualizes toolpath and allows manual jogging

Compatible with Windows, Linux, and macOS

✅ Inkscape (Design Tool)
Used to create vector graphics (.svg)

With J Tech Photonics Laser Tool Plugin, converts SVG paths into G-code

G-code exported in .gcode format

-----------------------------------------------------------------------------------
Axis Configuration
X-axis: Horizontal movement via stepper motor on threaded rod or GT2 belt

Y-axis: Vertical bed movement using second stepper

Z-axis: Pen lift/lower via servo motor

; Example G-code snippet
G21 ; Set units to mm
G90 ; Absolute positioning
G1 X10 Y10 F1000 ; Move to (10,10) at 1000 mm/min
M3 S90 ; Pen Down
G1 X50 Y50 F1000 ; Draw to (50,50)
M5 ; Pen Up
-----------------------------------------------------------------------------------

Build Highlights
Compact design, perfect for desktop drawing.

Pen mounted with zip ties or 3D-printed clamp.

Smooth X-Y movement with minimal backlash.

Servo attached to pin D11 (compatible with GRBL pin config).

----------------------------------------------------------------------------------
Testing and Calibration
Calibrated steps/mm using GRBL command: $$

Servo positions (Up/Down) controlled via M3/M5 with S values (like M3 S30, M5)

Drawing accuracy tested with simple square and circle paths
