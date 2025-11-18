# TH-D74 DV - User Guide

[![Version](https://img.shields.io/badge/version-2.6.1-blue.svg)](https://github.com/yourusername/thd74dv)
[![Platform](https://img.shields.io/badge/platform-Android-green.svg)](https://github.com/yourusername/thd74dv)
[![License](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)

A comprehensive D-STAR and APRS communication application for the Kenwood TH-D74/D75 handheld transceivers.

## 📱 Installation

1. Download the latest `.apk` file from the [Releases](https://github.com/rkarikari/TH-D74dv/releases) page
2. On your Android device, enable **Settings → Security → Unknown Sources**
3. Open the downloaded `.apk` file and follow the installation prompts
4. Grant Bluetooth and Location permissions when requested

![Chat Image](https://raw.githubusercontent.com/rkarikari/TH-D74dv/main/images/chat.jpg)
![DV Image](https://raw.githubusercontent.com/rkarikari/TH-D74dv/main/images/map.jpg)

## 🚀 Quick Start

### Initial Setup

1. **Pair Your Radio**
   - On your Android device: **Settings → Bluetooth → Pair new device**
   - On TH-D74: **Menu 930** → Set to **ON** (Enable Bluetooth)
   - Pair the devices using PIN: **0000**

2. **Configure Radio Bluetooth Settings**
   - Menu 982: **PC Output (APRS)** = Bluetooth
   - Menu 983: **KISS** = Bluetooth  
   - Menu 984: **DV/DR** = Bluetooth

3. **Launch App & Connect**
   - Open TH-D74 DV app
   - Go to **Settings** tab
   - Tap **Refresh Devices**
   - Select your TH-D74 from the list
   - Tap **Connect**

## 📋 User Interface Guide

The app features **7 tabs** accessible via swipe gestures or tab buttons at the top:

### 1. Messages Tab 💬

**Purpose:** Send and receive D-STAR and APRS chat messages

#### Sending Messages

1. **Enter recipient callsign** in the "To:" field
2. **Select message mode:**
   - **[D-STAR] Text (DATA Mode)** - For D-STAR data transmission (Rx only)
   - **[APRS] Chat (TNC Mode)** - For APRS messaging (recommended)
   - **[FILE] File Transfer** - Binary data transfer (Rx only)
   - **[GPS] Beacon (Auto)** - GPS position beacon
   - **[STATUS] Report** - Status message

3. **Type your message** in the text box
4. **Tap Send** button

#### Important Radio Setup

- **For APRS Chat** (recommended): 
  - Press **[TNC]** button on radio
  - Enable KISS mode
  - Set to APRS frequency (144.390 MHz in North America)

- **For D-STAR Text** (Rx only - receiving works):
  - Press **[DIGITAL]** button
  - Select **DATA** mode (not DV)
  - Menu 506: **Data Band** = A or B
  - Menu 984: **DV/DR** = Bluetooth

#### Message Features

- **Reply:** Tap the Reply button on received messages
- **Clear:** Remove all messages from display
- **GPS:** Send your current GPS position
- **Auto-scroll:** Messages automatically scroll to newest

---

### 2. APRS Tab 📡

**Purpose:** Full APRS protocol support with 20+ message types

#### GPS Quality Indicator
- **Excellent** (Green): ±5m accuracy
- **Good** (Light Green): ±10m accuracy  
- **Fair** (Yellow): ±20m accuracy
- **Poor** (Red): >20m accuracy

#### Sending APRS Messages

1. **Select Message Type** from dropdown (20+ types available):
   - Position reports (with/without timestamp)
   - Status messages
   - Direct messages
   - Bulletins & announcements
   - Weather reports
   - Objects & items
   - Telemetry & more

2. **Configure Parameters:**
   - **Course/Speed:** For moving position reports
   - **Object/Item Name:** For object reports (9 chars max)
   - **Message/Comment:** Your APRS message text

3. **Custom Templates:**
   - **Save:** Store frequently-used messages as templates
   - **Load:** Recall saved templates
   - **Delete:** Remove unwanted templates

4. **Auto Beacon:**
   - Enable checkbox to automatically transmit position
   - Set interval (1-60 minutes)
   - Uses your current GPS position

#### Radio Setup for APRS
- Press **[TNC]** button on radio
- Enable KISS mode  
- Set frequency to 144.390 MHz (North America) or local APRS frequency
- The app handles all APRS packet formatting

---

### 3. Path Tab 🛤️

**Purpose:** Configure APRS digipeater paths for message routing

#### Understanding Digipeater Paths

Digipeaters relay your APRS packets to extend range. The path determines which digipeaters will repeat your transmission.

#### Path Presets (Recommended)

- **Direct:** No digipeaters - local only
- **WIDE1-1:** Single hop via fill-in digipeater
- **WIDE1-1,WIDE2-1:** Mobile standard (recommended)
- **WIDE2-2:** Wide area coverage
- **WIDE2-1:** Single wide-area hop
- **ARISS:** Via satellite (ISS)

#### Using Presets

1. Select preset from dropdown
2. Read the description
3. Tap **Apply Preset**
4. Path preview shows how it will appear in packets

#### Custom Paths

1. **Enable/Disable Path:** Toggle checkbox at top
2. **Add Digipeater:**
   - Enter callsign (e.g., WIDE1, WIDE2)
   - Set SSID (0-15)
   - Tap **Add**
3. **Reorder:** Use Up/Down buttons
4. **Remove:** Select digipeater, tap **Remove**
5. **Clear All:** Remove all digipeaters

#### Path Guidelines

- 🟢 **0 hops (Direct):** Local coverage only
- 🟡 **1-2 hops:** Good for mobile/fixed stations
- 🟠 **3-4 hops:** Moderate - use sparingly
- 🔴 **5+ hops:** Excessive - causes network congestion

**Best Practice:** Use shortest path that meets your needs. Shorter paths reduce APRS network load.

---

### 4. Map Tab 🗺️

**Purpose:** Visual display of station locations with GPS positions

#### Features

- **Real-time Updates:** Map refreshes automatically every 5 seconds
- **Offline Capable:** Downloaded tiles cached for offline use
- **Station Markers:**
  - 🟢 **Green:** Your position
  - 🔴 **Red:** Other stations with GPS data

#### Controls

- **Zoom +/-:** Change map zoom level (1-18)
- **📍 My Position:** Center map on your GPS location
- **🌍 Show All:** Fit all stations in view
- **Pan:** Drag with finger (desktop: click and drag)
- **Pinch Zoom:** Two-finger gesture (mobile)

#### Statistics Panel

- **📡 Stations:** Number of plotted stations
- **🔍 Zoom:** Current zoom level
- **💾 Cache:** Number of cached map tiles
- **⬇ Queue:** Pending tile downloads

#### Tile Downloads

- Tiles download automatically as you pan/zoom
- Max 2 concurrent downloads (respects OpenStreetMap policy)
- 1 second minimum between requests
- Cache persists between app restarts
- **Clear Cache:** Delete all tiles to free space
- **Cache Info:** View cache statistics and location

#### Map Interaction

- **Tap marker:** View station callsign
- **Switch tabs:** Swipe left/right with single finger
- **First load:** May take time - tiles cache for future offline use

---

### 5. Contacts Tab 👥

**Purpose:** Manage your station contact list

#### Contact Cards

Each contact shows:
- **Callsign** (highlighted in blue)
- **📍 Position:** GPS coordinates (if available)
- **🕐 Last Seen:** Date and time of last contact
- **💬 Message Count:** Number of messages exchanged

#### Actions

- **Send Message:** Tap button on contact card (switches to Messages tab)
- **Add:** Manually add new contact by callsign
- **Delete:** Remove contact from list
- **Refresh:** Update contact card display
- **Export:** Save contacts as CSV file

#### Automatic Updates

Contacts are automatically created/updated when:
- Receiving D-STAR messages
- Receiving APRS packets
- GPS position updates received

---

### 6. Raw Tab 🔧

**Purpose:** Send manual commands and view radio responses

#### Features

- **Command Entry:** Type raw CAT commands
- **Response Display:** View radio responses in real-time
- **Test Connection:** Quick connectivity check
- **Command History:** Scrollable log of all commands/responses

#### Common Commands

- `ID` - Radio identification
- `FV` - Firmware version
- `AE` - Serial number
- `TX 1` - Activate PTT (Band A)
- `RX` - Release PTT

#### Debugging

- All Bluetooth communication logged here
- View APRS packet encoding/decoding
- Monitor D-STAR transmission status
- Check KISS frame processing

**Note:** Most users won't need this tab - it's for troubleshooting and advanced operations.

---

### 7. Settings Tab ⚙️

**Purpose:** Configure app and radio connection

#### Connection

1. **Refresh Devices:** Scan for paired Bluetooth devices
2. **Connect/Disconnect:** Toggle radio connection
3. **Status:** Shows current connection state

#### Station Info

- **Callsign:** YOUR callsign (required for APRS)
  - Format: CALL or CALL-SSID
  - Example: W1AW or KB6QWE-9
  - Used for all transmissions

#### Auto Reply

- **Enable:** Toggle automatic replies to received messages
- **Message:** Customize your auto-reply text
- **Clear Auto-Reply List:** Reset replied-to tracking

#### Save Settings

Tap **Save Settings** to persist configuration:
- Station callsign
- Auto-reply settings
- APRS path configuration
- All messages and contacts

---

## 🎯 Common Tasks

### Sending an APRS Message

1. **Settings Tab:** Enter your callsign
2. **Path Tab:** Select "WIDE1-1,WIDE2-1" preset (recommended for mobile)
3. **Messages Tab:** 
   - Select **[APRS] Chat (TNC Mode)**
   - Enter recipient callsign
   - Type message (max 67 chars)
   - Tap **Send**

### Sending Your GPS Position

1. **Wait for GPS fix** (green indicator in APRS tab)
2. **APRS Tab:**
   - Select "Position (No Messaging)" type
   - Add comment (optional)
   - Tap **Send APRS Message**

### Setting Up Auto GPS Beacon

1. **APRS Tab:**
   - Select position report type
   - Enable **Auto Beacon** checkbox
   - Set interval (e.g., 5 minutes)
   - Radio will beacon automatically

### Viewing Station Locations

1. **Map Tab:**
   - Wait for GPS positions to populate
   - Tap **🌍 Show All** to see all stations
   - Tap markers for station info

---

## ⚠️ Important Notes

### D-STAR Messages (DATA Mode)

**Current Status:** Receiving works, transmitting is experimental/unreliable

- App can **receive** D-STAR DATA mode messages successfully
- Transmitting via D-STAR DATA is not working reliably in current version
- **Recommendation:** Use APRS Chat for two-way messaging

### APRS Messages (TNC/KISS Mode)

**Fully Functional:** Both sending and receiving work perfectly

- Recommended mode for all text messaging
- Full APRS protocol support
- Reliable message delivery with ACK support
- Works with all APRS-capable stations

### GPS Requirements

- **Android GPS:** App uses your phone's GPS (not radio's internal GPS)
- **Permissions:** Must grant Location permission
- **Accuracy:** Displays GPS quality indicator in APRS tab
- **Position Types:** Some APRS message types require valid GPS position

---

## 🔧 Troubleshooting

### Connection Issues

**Problem:** Can't connect to radio
- ✅ Check Bluetooth is enabled on both devices
- ✅ Verify devices are paired (pair in Android Settings first)
- ✅ Radio Menu 930: Bluetooth = ON
- ✅ Try disconnect → close app → reopen → reconnect

**Problem:** Connected but no response
- ✅ Check Menus 982, 983, 984 set to Bluetooth
- ✅ Try "Test Connection" in Raw tab
- ✅ Power cycle the radio

### APRS Issues

**Problem:** Messages not sending
- ✅ Radio in **[TNC]** mode with KISS enabled
- ✅ Set to correct APRS frequency (144.390 MHz)
- ✅ Check Raw tab for transmission confirmation
- ✅ Verify path configuration (or use Direct)

**Problem:** Not receiving APRS
- ✅ Radio squelch properly adjusted
- ✅ On correct frequency
- ✅ KISS mode enabled
- ✅ Check Raw tab for received frames

### GPS Issues

**Problem:** No GPS fix
- ✅ Grant Location permission to app
- ✅ Ensure Android Location Services enabled
- ✅ Go outdoors or near window
- ✅ Wait 30-60 seconds for satellite lock

**Problem:** Stale GPS data
- ✅ Check GPS timestamp in APRS tab
- ✅ Verify Location permission not restricted
- ✅ Try toggling airplane mode off/on

### Map Issues

**Problem:** Tiles not loading
- ✅ Check internet connection
- ✅ Wait - downloads limited to 2 concurrent
- ✅ Check ⬇ Queue indicator
- ✅ Try zooming in/out to trigger refresh

**Problem:** Map performance slow
- ✅ Too many cached tiles - tap "Clear Cache"
- ✅ Close other apps to free memory
- ✅ Restart app

---

## 📊 Features Summary

| Feature | Status |
|---------|--------|
| APRS Messaging | ✅ Full Support |
| APRS Position Beacons | ✅ Full Support |
| APRS Path Configuration | ✅ Full Support |
| D-STAR Receive (DATA) | ✅ Working |
| D-STAR Transmit (DATA) | ⚠️ Experimental |
| GPS Integration | ✅ Full Support |
| Map Display | ✅ Full Support |
| Contact Management | ✅ Full Support |
| Auto-Reply | ✅ Full Support |
| Custom Templates | ✅ Full Support |
| Offline Map Tiles | ✅ Full Support |

---

## 📄 Version History

### v2.6.1 (Current)
- Improved APRS reliability
- Enhanced GPS accuracy display
- Fixed map tile caching
- Better error handling
- UI improvements for Android

### v2.2
- Complete APRS protocol support
- 20+ APRS message types
- Custom message templates
- Digipeater path configuration
- Map display with OpenStreetMap

---

## 🤝 Support

- **Developer:** 9G5AR
- **Organization:** RNK, RadioSport Development
- **Year:** 2025

For issues, questions, or contributions, please open an issue on GitHub.

---

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🙏 Acknowledgments

- OpenStreetMap contributors for map tiles
- APRS protocol specification authors
- Qt framework developers
- Kenwood for TH-D74/D75 documentation

---

**73 de 9G5AR** 📻
