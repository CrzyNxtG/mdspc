### 5.14.7 UDC buffer reset procedure

UDC works on the condition that compression buffer and de-compression
buffer are synchronized. UDC buffer reset mechanism is to resynchronize
buffer when error is detected. For resynchronization, UE shall reset the
compression buffer to all zeros.