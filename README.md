# WhatsApp Baileys

<p align="center">
  <img src="https://files.catbox.moe/k09cwz.jpg" alt="Thumbnail" />
</p>

WhatsApp Baileys is an open-source library designed to help developers build automation solutions and integrations with WhatsApp efficiently and directly. Using websocket technology without the need for a browser, this library supports a wide range of features such as message management, chat handling, group administration, as well as interactive messages and action buttons for a more dynamic user experience..

Actively developed and maintained, baileys continuously receives updates to enhance stability and performance. One of the main focuses is to improve the pairing and authentication processes to be more stable and secure. Pairing features can be customized with your own codes, making the process more reliable and less prone to interruptions.

This library is highly suitable for building business bots, chat automation systems, customer service solutions, and various other communication automation applications that require high stability and comprehensive features. With a lightweight and modular design, baileys is easy to integrate into different systems and platforms.

---

### Main Features and Advantages

- Supports automatic and custom pairing processes
- Fixes previous pairing issues that often caused failures or disconnections
- Supports interactive messages, action buttons, and dynamic menus
- Efficient automatic session management for reliable operation
- Compatible with the latest multi-device features from WhatsApp
- Lightweight, stable, and easy to integrate into various systems
- Suitable for developing bots, automation, and complete communication solutions
- Comprehensive documentation and example codes to facilitate development

---

## Getting Started

Begin by installing the library via your preferred package manager, then follow the provided configuration guide. You can also utilize the ready-made example codes to understand how the features work. Use session storage and interactive messaging features to build complete, stable solutions tailored to your business or project needs.

## How To Usage?
```json
"depencies": {
  "@whiskeysockets/baileys": "github:Fhkryy/XV-Baileys"
}
```
## Import
```javascript
const {
  default:makeWASocket,
  // Other Options 
} = require('@whiskeysockets/baileys');
```

---
# How To Connect To Whatsapp
## With QR Code
```javascript
const {
  default: makeWASocket
} = require('@whiskeysockets/baileys');

const Fhkryy = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: true
})
```

## Connect With Number
```javascript
const {
  default: makeWASocket,
  fetchLatestWAWebVersion
} = require('@whiskeysockets/baileys');

const Fhkryy = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion()
  // Other options
});

const number = "628XXXXX";
const code = await Fhkryy.requestPairingCode(number.trim) /* Use : (number, "YYYYYYYY") for custom-pairing */

console.log("Ur pairing code : " + code)
```

# Sending messages

## send orderMessage
```javascript
const fs = require('fs');
const nameImg = fs.readFileSync('./YourImage');

await Fhkryy.sendMessage(m.chat, {
  thumbnail: YourImg,
  message: "Gotta get a grip",
  orderTitle: "HaveANiceDay",
  totalAmount1000: 8888,
  totalCurrencyCode: "IDR"
}, { quoted:m })
```

## send pollResultSnapshotMessage
```javascript
await Fhkryy.sendMessage(m.chat, {
  pollResultMessage: {
    name: "Fhkryy pollMessage",
    options: [
      {
        optionName: "FhkryX Ganteng"
      },
      {
        optionName: "Binzz Eek"
      }
    ],
    newsletter: {
      newsletterName: "FhkryX",
      newsletterJid: "1@newsletter"
    }
  }
})
```

## send productMessage
```javascript
await Fhkryy.relayMessage(m.chat, {
  productMessage {
    title: "FhkryX",
    description: "Fhkryy",
    thumbnail: { url: "linkCatboxTourl" },
    productId: "PRODUCT_TOKEN",
    retailerId: "EXAMPLE_RETAILER_ID",
    url: "https://t.me/Fhkry666",
    body: "Fhkryy",
    footer: "FhkryX",
    buttons: [
      {
        name: "cta_url",
        buttonParamsJson: "{\"display_text\":\"Fhkryy\",\"url\":\"https://t.me/Fhkry666\"}"
      }
    ],
    priceAmount1000: 72502,
    currencyCode: "IDR"
  }
})
```