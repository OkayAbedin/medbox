# MedBox Hall Effect Sensor Operation Guide

## How the KY-024 Works with MedBox

![KY-024 Hall Effect Sensor](https://imgaz.staticbg.com/images/oaupload/banggood/images/B6/C8/360765ff-7d48-413b-8dea-399c85ea4e5f.jpg)

### Lid State and LED Behavior

| Lid State | Magnet Position | Sensor Reading | MedBox LED | Action |
|-----------|----------------|-----------------|-------------|---------|
| **CLOSED** | Near Sensor | **LOW (0)** | **OFF** | Normal operation |
| **OPEN** | Away from Sensor | **HIGH (1)** | **BLUE** | Blue LED stays on, alarms cleared |

### Expected Behavior

1. **When Lid is Closed**:
   - The magnet on the lid is close to the KY-024 sensor
   - The sensor reads **LOW (0)**
   - MedBox LED is **OFF** (normal state)
   - Normal operation continues (alarms can be active)

2. **When Lid is Opened**:
   - The magnet moves away from the KY-024 sensor
   - The sensor reads **HIGH (1)**
   - MedBox LED turns **BLUE** and stays blue while the lid is open
   - Any active alarm for that compartment will be cleared

### Alarm Behavior

- **Active Alarm + Lid Closed**:
  - Red blinking LED on MedBox
  - Buzzer beeping

- **Active Alarm + Lid Opened**:
  - Blue LED on MedBox (indicates lid is open)
  - Buzzer stops
  - Alarm cleared automatically

- **After Opening and Closing Lid**:
  - LED turns off when lid is closed
  - Normal operation resumes

## Installation Tips

1. **Mount the KY-024 Module**:
   - Position the sensor on the MedBox frame
   - The component side should face where the lid will close

2. **Attach Magnet to Lid**:
   - Secure a small magnet to the underside of each lid
   - Position it to align directly with the KY-024 module when closed

3. **Sensitivity Adjustment**:
   - Use the blue potentiometer on the KY-024 module to adjust sensitivity
   - Turn clockwise to increase sensitivity (detect magnet from further away)
   - Turn counterclockwise to decrease sensitivity (require magnet to be closer)
   - Proper calibration: You should get a LOW reading when lid is closed, HIGH when opened

## Testing Your Setup

1. **Basic Functionality Test**:
   - Close all lids and verify MedBox LEDs are OFF
   - Open each lid one by one and verify the MedBox LED turns BLUE when opened
   - The system should print debug messages confirming lid state changes

2. **Alarm Clearing Test**:
   - Set up an alarm for the current time
   - When the alarm activates, the MedBox LED will blink red
   - Open the compartment and verify:
     - MedBox LED turns blue
     - Alarm clears
   - Close the compartment and verify the LED turns off
