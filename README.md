# Typing Buddy: Feline-Integrated Input System

**Typing Buddy** is a hardware and software integration designed to allow a feline companion to interface with a computer system, enabling them to type in synchronization with the user. This project utilizes an Arduino-based mechanical rig and a background executable to bridge the gap between physical movement and digital input.

## System Overview

The system operates via a dual-layer architecture:

* **Hardware Layer:** An Arduino microcontroller manages the mechanical motor and key mechanisms.
* **Software Layer:** A Python script running on the host computer coordinates the interaction between user input and hardware response.

---

## 🛠 Preparation and Procurement

### 3D Printing Guidelines

Precision in the printing process is critical for the mechanical functionality of the system.

* **Base Accuracy:** Prioritize the accuracy of the base component; it is the foundation for the entire assembly.
* **Cat Paws/Arms:** Print with the paw pads on the bed (approx. 30° to 45° angle). This has been verified to print successfully on entry-level hardware like the Anycubic Kobra Neo.
* **ZERO INFILL:** It is mandatory to set the **infill to 0%** for the cat model. The internal volume must remain hollow to house the hardware.

### Equipment Acquisition

* **Bulk Sets:** Most components are sold in sets. The quantity of parts in standard sets makes it efficient to produce three units simultaneously.
* **Key Caps:** It is strongly recommended to purchase manufactured key caps. Attempting to 3D print caps and source individual keys is significantly more complex.

---

## 💻 Software Implementation

The project requires active code on both the Arduino and the host PC.

### 1. Arduino Configuration

* **Pin Assignments:** The code uses **Pin 9 and Pin 10** for motor speed and direction.
* **Customization:** Users can modify `run time` and `motor speed` variables at the start of the script.

### 2. Python Configuration

* **Communication Port:** Currently configured for **COM4**. Update this variable to match your Arduino's assigned port.
* **Baud Rate:** Set to **9600**.
* **System Augmentations:** Originally developed for integrated laptop keyboards. For USB-based external keyboards, you may need to run the script through an LLM (like Claude) for specific driver modifications.

### 3. Execution

* **Manual:** Initiate the script via PowerShell.
* **Automated:** Implement a `.bat` file in your startup folder to trigger the code automatically upon boot.

---

## 🔧 Mechanical Assembly and Modification

### Model Preparation

1. **Base Removal:** With **ZERO INFILL**, you can pull off the bottom layers of the cat print to leave the internal cavity open.
2. **Stomach Excavation:** Use a soldering iron to cut out the stomach section following the pre-designed indent. Remember: cut conservatively.
3. **Cable Pocket:** Use a soldering iron to cut a custom pocket where the Arduino USB cable exits for a more compact design.
4. **Aesthetics:** Facial features can be added manually using a permanent marker.

### Motor and Hinge Assembly

* **Floss Tie-Down:** Thread high-strength floss through the hole at the top of the motor. Pull it down into the cavity and tie it to the main structure. This prevents the motor from "pushing out" during use.
* **Hinge:** Insert a **16-gauge wire** through the arm holder to act as the dowel for the hinge mechanism.
* **Stabilization:** If the motor twists under torque, insert a secondary piece of 16-gauge wire (or use putty/glue) to lock it in place.

---

## ⚠️ Operational Notes

**The Escape Key "Kill Switch"**
The Escape key is programmed as the global termination command. If pressed, the script stops immediately and requires a manual restart. Users of CAD software should be especially mindful of this hardcoded functionality.

---

## 🔍 Troubleshooting

* **Scaling:** If parts do not mesh, minor scaling adjustments in your slicer may be necessary.
* **Motor Torque:** If the motor shifts clockwise/counter-clockwise, reinforce the tie-downs or use a 16-gauge wire brace.
* **Inconsistency:** Ensure the 16-gauge hinge wire moves freely and isn't snagging on the hollow cat shell.

## 🚀 System Augmentations

Users can further improve this model by:

* Developing a dedicated PCB to replace breadboard prototyping.
* Engineering a more compact design for the motor and key mechanisms.
* Optimizing structural holding materials for a smaller footprint.
