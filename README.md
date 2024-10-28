# Atom Ducky Clone for atom s3 lite device. 

This repository is a customized version of the Atom Ducky project, with added files for the Atom Ducky BLE edition, esptool, and a combined firmware (combined.bin) for the Atom S3 Lite device. 
Additionally, the repository includes an adafruit-circuitpython uf2 file.

# Setup Instructions (last updated 2024 28th oct)

1. Download All files from this repository
2. Open cmd prompt in the esptool-win64 folder
3. connect your m5stick atom s3 lite device and type the following commands.

```
  # Find the port

  # Windows:
  $ mode
  # Look for devices that have 9600-460800 Baud
      Status for device COM13:            (COM13 is port)
      ------------------------
          Baud:            9600
          Parity:          None
          Data Bits:       8
          Stop Bits:       1.5
          Timeout:         OFF
          XON/XOFF:        OFF
          CTS handshaking: OFF
          DSR handshaking: OFF
          DSR sensitivity: OFF
          DTR circuit:     OFF
          RTS circuit:     OFF

  # Linux:
  dmesg | grep tty
```

4. Enter the below commands with the above port changed.
```
  $ esptool --port COM13 erase_flash
  $ esptool --port COM13 --baud 460800 write_flash -z 0 combined.bin
```
5. Note the combined.bin file will be inside the esptool-win64 folder.
6. There should be a new drive detected by your computer now
7. now copy the "adafruit-circuitpython-m5stack_atoms3_lite-en_US-9.1.4.uf2" file to that newly detect drive.
8. after that the device will boot again with circuit.py name
9. now drag and drop the files inside folder AtomDucky_no_ble
10.Thats it the rubber ducky is ready and remove the device and plug it in a device where you want to run the commands.
   
11.Now it will generate a wifi name ```cyberblockz``` and password ```passw1234``` connect with that wifi and control the keystroks and payloads.

Credits
This project is based on the original [Atom Ducky](https://github.com/FLOCK4H/AtomDucky/tree/main) repository, and all credits for this goes to the original creators.


