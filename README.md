# tpImageEditor
TP-LINK Image Editor tool

# Work in Porgress  
Missing fields:  
- Unknown MD5  
- Unknown 128 bytes  

## Firmware structure
| Size (byte)  | Name | Description |
| :----------: | ---- | ------- |
| 512 | TP-TAG (header) | Described below |
| ? | Body | Firmware payload (Broadcom Image) |  

## TP-TAG (header) structure  
| Size (byte)  | Type | Name | Description |
| :----------: | ---- | ---- | ------- |
|   4 | UBE Int | Tag Version | Eg: 1 |
|  24 | String  | Company | Text line for company info, Eg: TP-LINK Technologies |
|  12 | String  | Software Version | Eg: ver.1.1.1 |
|   8 | String  | Chip ID | Eg: 6328 |
|  16 | String  | Board ID | Eg: W8968 |
|   4 | UBE Int | Product ID | Eg: 0x08968000 |
|   4 | UBE Int | Product Version | Eg: 4 |
|   4 | UBE Int | Hardware Version | Eg: 0x00000001 |
|  16 | Byte array | Body MD5 | MD5 of all body's bytes |
|  4  | Byte array | Unknown | Eg: 0x00000000 |
|  16 | Byte array | Unknown MD5 | MD5 of ? |
|  12 | Byte array | Unknown | Eg: 0x00000000 0x00000000 0x00000000) |
|   4 | UBE Int | Body size | Length in bytes of body |
|   4 | Byte array | Unknown | Eg: 0x00000000 |
|   4 | UBE Int | Fixed Kernel Length | Fixed value: 692 |
|   4 | Byte array | Unknown | Eg: 0x00000000 |
|   4 | UBE Int | Fixed RootFS Length | Fixed value: 2854912 |
|   4 | Byte array | Unknown | Eg: 0x00000000 |
|   4 | UBE Int | Fixed CFE Length | Fixed value: 65536 (sometimes 0) |
| 128 | Byte array | Unknown | 1024 bit very random |
| 232 | Byte Array | Offset | Offset to 512 bytes |
