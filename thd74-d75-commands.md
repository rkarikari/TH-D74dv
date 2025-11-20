# Kenwood TH-D74/TH-D75 Raw Commands Reference

## Command List

| Code | Description | Example Usage |
|------|-------------|---------------|
| **AE** | Radio serial number and model | `AE` - Query radio information |
| **AG** | AF Gain (Audio/Volume) | `AG0,050` - Set Band A volume to 50<br>`AG1,025` - Set Band B volume to 25 |
| **AI** | Realtime feedback on frequency change | `AI0` - Disable auto info<br>`AI1` - Enable auto info |
| **AS** | TNC baud rate | `AS0,0` - Set TNC baud rate |
| **BC** | PTT and CTRL Band | `BC0` - Set Band A as PTT/CTRL<br>`BC1` - Set Band B as PTT/CTRL |
| **BE** | APRS Beacon | `BE0` - Beacon off<br>`BE1` - Beacon on |
| **BL** | Battery level | `BL` - Query battery level (returns 0-15) |
| **BS** | Bar antenna | `BS0` - Bar antenna off<br>`BS1` - Bar antenna on |
| **BT** | Bluetooth | `BT0` - Bluetooth off<br>`BT1` - Bluetooth on |
| **BY** | Squelch open/closed | `BY0` - Query Band A squelch<br>`BY1` - Query Band B squelch |
| **CS** | Callsign | `CS` - Query callsign<br>`CS,MYCALL` - Set callsign |
| **DC** | D-Star slot, callsign, message | `DC0` - Query D-Star slot 0 info |
| **DL** | Dual Band Mode/Single Band Mode | `DL0` - Single band mode<br>`DL1` - Dual band mode |
| **DS** | D-Star callsign slot | `DS0` - Select D-Star slot 0 |
| **DW** | Emulates Microphone Down Key | `DW` - Simulate down key press |
| **FO** | VFO channel | `FO0` - Select VFO A<br>`FO1` - Select VFO B |
| **FQ** | Frequency | `FQ0,146520000` - Set Band A to 146.520 MHz<br>`FQ1,446000000` - Set Band B to 446.000 MHz |
| **FR** | FM radio | `FR0` - FM radio off<br>`FR1` - FM radio on |
| **FS** | Fine step | `FS0` - Disable fine step<br>`FS1` - Enable fine step |
| **FT** | Fine tuning status | `FT` - Query fine tuning status |
| **FV** | Firmware version | `FV` - Query firmware version |
| **GM** | Radio/GPS mode | `GM0` - Radio mode<br>`GM1` - GPS mode |
| **GP** | Internal GPS | `GP0` - GPS off<br>`GP1` - GPS on |
| **GS** | GPS sentence | `GS` - Request GPS NMEA sentence |
| **ID** | Radio Model | `ID` - Query radio model ID |
| **IO** | Get/set IF output mode | `IO0` - IF output off<br>`IO1` - IF output on |
| **LC** | Display light | `LC0` - Display light off<br>`LC1,5` - Display light on, level 5 |
| **MD** | Mode (modulation) | `MD0,0` - Band A FM mode<br>`MD0,1` - Band A AM mode<br>`MD0,2` - Band A DR (D-STAR)<br>`MD0,3` - Band A LSB<br>`MD0,4` - Band A USB<br>`MD0,5` - Band A CW |
| **ME** | Memory channel (frequency, offset, etc) | `ME0,001` - Read memory channel 001<br>`ME0,001,146520000,0,0,0,08,08,00,00,0,0,0,0` - Write memory |
| **MR** | Memory channel recall | `MR0,001` - Recall memory channel 001 on Band A |
| **MS** | My position (APRS) | `MS` - Query my position<br>`MS,3759.12N,12159.34W` - Set position |
| **PC** | Output power | `PC0,3` - Band A High power<br>`PC0,2` - Band A Medium<br>`PC0,1` - Band A Low<br>`PC0,0` - Band A Extra Low |
| **PS** | Master power | `PS0` - Power off<br>`PS1` - Power on |
| **PT** | Beacon control | `PT0` - APRS beacon off<br>`PT1` - APRS beacon on |
| **RA** | Attenuator | `RA00` - Attenuator off<br>`RA01` - Attenuator on |
| **RT** | Time (clock) | `RT` - Query time<br>`RT,1200` - Set time to 12:00 |
| **RX** | Receive (end transmit) | `RX` - Switch to receive mode |
| **SF** | Receive step size | `SF0,05` - Band A 5 kHz step<br>`SF0,25` - Band A 25 kHz step |
| **SH** | Filter cutoff | `SH0,0` - Band A wide filter<br>`SH0,1` - Band A mid filter<br>`SH0,2` - Band A narrow filter |
| **SM** | S-meter | `SM0` - Read Band A S-meter<br>`SM1` - Read Band B S-meter |
| **SQ** | Squelch status | `SQ0,05` - Band A squelch level 5<br>`SQ1,10` - Band B squelch level 10 |
| **SR** | Reset | `SR0` - VFO reset<br>`SR1` - Full reset |
| **TN** | KISS TNC | `TN0,0` - TNC off<br>`TN1,0` - TNC on |
| **TX** | Transmit | `TX` - Start transmitting<br>`TX0` - Transmit on Band A<br>`TX1` - Transmit on Band B |
| **TY** | Radio Type | `TY` - Query radio type/region |
| **UP** | Emulates Microphone Up Key | `UP` - Simulate up key press |
| **VD** | VOX delay | `VD0,500` - Set VOX delay to 500ms |
| **VG** | VOX Gain | `VG0,5` - Set VOX gain level 5 |
| **VM** | Memory/VFO mode | `VM0,0` - Band A VFO mode<br>`VM0,1` - Band A Memory mode |
| **VX** | VOX on/off | `VX0` - VOX off<br>`VX1` - VOX on |
| **0M PROGRAM** | Enter MCP programming mode | `0M PROGRAM` - Enter programming mode (0=ZERO, M=MIKE) |
| **0G KENWOOD** | Enter service mode | `0G KENWOOD` - Enter service mode (0=ZERO, G=GOLF) ⚠️ WARNING: Can make radio unusable! |

## Notes

1. **Command Format**: Commands are typically 2 characters followed by parameters separated by commas
2. **Band Parameter**: 
   - `0` = Band A
   - `1` = Band B
3. **Frequency Format**: Frequencies are specified in Hz (e.g., 146520000 = 146.520 MHz)
4. **Termination**: Commands should be terminated with a carriage return (CR)
5. **Query vs Set**: Commands without parameters typically query current settings; with parameters they set values
6. **Compatibility**: These commands work on both TH-D74 (A/E/K) and TH-D75 (A/E) models
7. **⚠️ CAUTION**: The service mode commands (`0G KENWOOD`) can permanently damage your radio if used incorrectly

## Communication Settings

- **Baud Rate**: 9600 bps (default for PC connection)
- **Data Bits**: 8
- **Stop Bits**: 1
- **Parity**: None
- **Flow Control**: None
- **Interface**: USB (appears as serial port) or Bluetooth

## Example Usage Sequence

```
AI1              # Enable auto-info mode
FQ0,146520000    # Set Band A to 146.520 MHz
MD0,0            # Set Band A to FM mode
PC0,3            # Set Band A to High power
TX0              # Start transmitting on Band A
RX               # Stop transmitting
```

## Resources

- Full command documentation: [LA3QMA TH-D74-Kenwood GitHub Repository](https://github.com/LA3QMA/TH-D74-Kenwood)
- Each command has detailed documentation in the commands folder
- Firmware version referenced: V1.10+

---

*Command list compiled from reverse-engineered documentation by LA3QMA and contributors*  
*Always refer to official Kenwood documentation for safety-critical operations*