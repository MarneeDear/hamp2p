# VHF Paket Radio

## APRS with FLDIGI

Protocol for using APRS and FLDIGI to share files over VHF.


## APRS plus IPFS and FLDIGI

Operator free operation protocol for sharing files using IPFS and ham radio as the transport.

### Dependencies

| Dependency | Purpose | Comments |
| -------- | -------- | -------- |
| IPFS     | Text     | Text     |
| FLDIGI   |          |          |
| DireWolf |          |          |
| Chickadee |         |          |



### Transmitting station

1. APRS Transmit request to share file. User defined format
    1. APRS Use APRS Message format See APRS 101 
2. APRS Wait for ACK from a receiving station
3. APRS Start sending the IPFS file hash
    1. APRS Wait for ACK of each segment
    2. APRS Continue until all segments are ACKed
4. Send signal that file will transmit
5. Fire up FLDIGI and start sending the file
6. APRS Wait for ACK that the file was recevied. User defined format
7. IPFS save file to storage and share over other transports -- TCP for example

### Receiving stations

1. APRS Receive request to share file.
2. Send ACK ready to receive
3. Wait for IPFS file hashes
4. Record IPFS file hashes and concatenate into final hash
5. Wait for signal that file is transmitting
6. Fire up FLDIGI and receive file
7. Save file to IPFS with the hash


