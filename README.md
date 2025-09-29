
## 🚀 See More. Sense More. Automate Like Never Before.

![Sensy-One Banner](https://github.com/sensy-one/E1/blob/main/assets/images/banner-e1.jpg)

Introducing the Sensy-One E1 – the smallest and most powerful mmWave sensor on the market.
After months of prototyping, fine-tuning the firmware, and testing, we have developed a sensor that sets a new performance standard. The E1 delivers near-instant motion detection, exceptional accuracy, and seamless Home Assistant integration. [Explore on YouTube](https://www.youtube.com/watch?v=tJVh7_wXfik)

## ✨ Standout Specs

**Instant Home Assistant Integration**  

Power it up, plug it in — and it just works. The E1 connects instantly to Home Assistant over wired Ethernet using PoE or Ethernet + USB-C 5V. No wireless setup, no BLE, no hassle. Just reliable, rock-solid integration from the moment it powers on.

**Precision Motion Tracking**  

Track up to three targets simultaneously in real time. The Hi-Link LD2450 accurately detects X and Y coordinates, movement speed, and more, with a 6-meter range, 120° field of view, and a 35° pitch angle. Whether detecting subtle movements or following dynamic motion, you can count on precise, reliable performance.

**Customizable Detection Zones**  

Our sensor offers flexible monitoring with up to 10 customizable detection zones and one exclusion zone. Each detection zone includes three dedicated sensors that measure movement, presence, and target count, providing detailed insights into activity. Adjustable motion thresholds and timeouts allow you to fine-tune the sensor’s sensitivity and response, ensuring optimal performance in any environment.

**Power-Packed Performance**  

At its core, the E1 runs on an ESP32-S3 with a dedicated PoE module, delivering dual-core processing power and real-time data handling — all over wired Ethernet. Expect lightning-fast response times, ultra-reliable automations, and rock-solid performance without relying on Wi-Fi.

**Compact Design**  

Measuring just 25 mm × 30 mm × 75 mm, the E1 proves that powerful sensing doesn’t need a big footprint. It comes with a Command™ Velcro Strip for quick, flexible mounting — no screws, no drilling.

## ⚡ From Power On to Home Assistant

Powering the E1 is as simple as plugging it in via PoE or using Ethernet + USB-C 5V. No wireless setup, no configuration portals — just plug and go. As soon as the E1 powers on and is connected to your network, it automatically appears in Home Assistant under Devices and Services as Discovered. Click Add, and you’re ready to automate.

## 📊 Real-Time Visualization with Plotly Graph Card

Add an interactive map to your Home Assistant dashboard. The Plotly Graph Card automatically displays live target positions, speeds, and any zones you’ve configured. Offering at-a-glance insights into every movement.

**Install HACS and the Plotly Graph Card**  
- If you haven’t already installed HACS, follow the [Official instructions](https://www.hacs.xyz/docs/use/download/download/).
- Once HACS is installed, open it in Home Assistant.
- Search for and install the **Plotly Graph Card** integration.

**Add a Custom Plotly Graph Card**  
- Go to your Home Assistant dashboard and click **Edit Dashboard**.
- Select **Add Card** and choose **Plotly Graph Card**.
- Click **Show Code Editor** to open the YAML configuration editor.
- Copy and paste the custom configuration from the [Git repository](https://github.com/sensy-one/E1/blob/main/assets/config/) into the editor.

**Replace the Placeholder IDs**  
- Use your text editor’s find & replace feature (usually **Ctrl+F** on Windows or **Command+F** on Mac) to locate any `replace_me` placeholders in the YAML configuration.
- Replace them with your sensor name. By default, this might be `sensy_one_1617c8`. If you renamed the sensor (e.g., “Living Room”), use `living_room`.
- If you see a **Visual editor not supported** message, you can safely ignore it. This is normal for custom cards.

## 📍 Get in the Zone

The E1 now supports up to 3 detection zones and 1 exclusion zone — all configurable as custom polygons with up to 8 points each.
Instead of adjusting multiple number entities, you can now set zones visually using the Zone Editor tool:

**How to use the Zone Editor**
- Download the [zone_editor.html](https://github.com/sensy-one/E1/tree/main/assets/config) file.
- Open the Zone Editor on a desktop computer using any modern browser (Chrome, Edge, Firefox, Safari).
- In the Zone Editor, enter the IP address of your S1 Pro (the same one you see in Home Assistant).
- Select which zone you want to configure (Zone 1, Zone 2, Zone 3, or Exclusion).
- Click directly on the radar canvas to place up to 8 points and draw the shape of your zone.
- Save your configuration — it will be applied immediately to your device.

> Note: Make sure your desktop is connected to the same network as your Home Assistant / Sensor.

## 🔄 Firmware on the Fly

Keep your sensor up to date with regular OTA updates. We continuously refine performance and add new functionalities to keep your sensor reliable and current.

**Install OTA Updates**  
- Download the latest OTA firmware from the [releases](https://github.com/sensy-one/E1/releases).
- Go to **Devices and Services** and select **ESPHome**. Choose the sensor you want to update.  
- Under **Device Info**, click **Visit** to open the sensor’s web server.
- Scroll down to the **OTA Update**, choose the downloaded firmware file, and click **Update**.  
  *(If the update page times out, simply refresh the page.)*

## ⚙️ Build Your Own Solution

For advanced users looking to create custom firmware, simply integrate the settings below into your yaml.

```yaml
esp32:
  board: esp32-s3-devkitc-1
  framework:
    type: arduino
    version: 2.0.9

ethernet:
  type: W5500
  mosi_pin: GPIO11
  miso_pin: GPIO12
  clk_pin: GPIO13
  cs_pin: GPIO14
  reset_pin: GPIO9
  interrupt_pin: GPIO10
  clock_speed: 25MHz

uart:
  id: uart_ld2450
  tx_pin: GPIO37
  rx_pin: GPIO38
  baud_rate: 256000
  parity: NONE
  stop_bits: 1
```

## 🔧 Troubleshooting

Even the most cutting-edge tech can have its off moments. If your sensor isn’t performing exactly as expected, don’t worry. A quick factory reset might be all you need for a fresh start.

**Install Factory Firmware**  
- Download the latest factory firmware from the [releases](https://github.com/sensy-one/E1/releases).
- Plug the sensor into your PC via USB-C.  
- Open the [Official ESPHome Web Wizard](https://web.esphome.io/?dashboard_wizard).  
- Click **Connect** and select the appropriate COM port for your sensor.  
- Click **Install**, choose the downloaded firmware file, and click **Install** once more.

## 💬 Let's Connect

Your feedback fuels our innovation. Whether you're encountering a hiccup or have a brilliant idea to share, we're here to listen.

**Discord:**  
- Chat with our community and get instant help on our [Discord server](https://discord.gg/TB78Wprn66).

**GitHub Issues:**   
- Encountered a bug or have a suggestion? Report it on our [GitHub Issues page](https://github.com/sensy-one/E1/issues).