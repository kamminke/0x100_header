# 0x100_header
Registerfile Informational Header for Open Source Cores

## Offset 0x00: Endianness

As https://en.wikipedia.org/wiki/Endianness said:
> Endianness refers to the sequential order in which bytes are arranged into larger numerical values.

- Big Endian
- Little Endian

## Offset 0x01 - 0x0F: Core Name

- \0 terminated UTF-8 String
- no names longer than 15 Byte Characters, Offset 0x0F is alwasys Zero (\0)

## Offset 0x10 - 0x17: Revision Number

See https://en.wikipedia.org/wiki/Software_versioning

- BCD encoded
- 32-bit Major Version
- 32-bit Minor Version

or:
- git SHA1-Hash

## Offset 0x18 - 0x1F: Time Stamp

See https://en.wikipedia.org/wiki/Unix_time

- 64-bit time_t Epoch Time
- generated by Build Environment (eg. Make) before Synthesis Run

## Offset 0x20 - 0x2F: SoC-Bus Interface

- Kind of Bus (Wishbone, AMBA..)
- Bus Spec Version
- Bus Width
- Bursts?
- Tags?

## Offset 0xE0 - 0xFF: HDL Source Code Hash Sum

- SHA256 Hash Sum over complete HDL Source Code
- generated by Build Environment (eg. Make) before Synthesis Run
