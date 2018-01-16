# LoRa-HelloByte
Sends a small, airtime-saving ID message (1 Byte) from an Arduino Mega/Dragino Node to The Things Network

##Setup

1. Arduino Mega 2560
2. Dragino LoRa Shield v. 14
3. A TTN Account with respective Keys for your Application & Device

## Decoder Function
Use the following function to decode your byte (in TTN->Application->Payload Formats)

```
function Decoder(bytes, port) {
  var decoded = {};

//for strings
//decoded.message = String.fromCharCode.apply(null, bytes);

//for bytes
if (port === 1) decoded.id = bytes[0];

return decoded;
}
```
