### 5.14.8 UDC checksum error handling

UDC checksum error notification PDCP control PDU indicates the
compression buffer and de-compression buffer are out of synchronization.
When receiving the notification, the UE shall trigger UDC buffer reset
procedure to resynchonize the compression buffer.