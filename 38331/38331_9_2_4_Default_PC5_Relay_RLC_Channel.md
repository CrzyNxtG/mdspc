### 9.2.4 Default PC5 Relay RLC Channel

Parameters of the PC5 Relay RLC Channel used for Remote UE\'s SRB1 RRC
message transmission and reception. The PC5 Relay RLC Channel using this
configuration is named as SL-RLC1.

  ----------------------------------------------------------------------------
  Name                         Value       Semantics description    Ver
  ---------------------------- ----------- ------------------------ ----------
  RLC configuration                        AM                       

  *\>sn-FieldLength*           12                                   

  *\>t-Reassembly*             Undefined   Selected by the receving 
                                           UE, up to UE             
                                           implementation           

  *\>t-PollRetransmit*         Undefined   Selected by the          
                                           transmitting UE, up to   
                                           UE implementation        

  *\>pollPDU*                  Undefined   Selected by the          
                                           transmitting UE, up to   
                                           UE implementation        

  *\>pollByte*                 Undefined   Selected by the          
                                           transmitting UE, up to   
                                           UE implementation        

  *\>maxRetxThreshold*         Undefined   Selected by the          
                                           transmitting UE, up to   
                                           UE implementation        

  *\>t-StatusProhibit*         Undefined   Selected by the          
                                           receiving UE, up to UE   
                                           implementation           

  *\>logicalChannelIdentity*   57                                   

  MAC configuration                                                 

  *\>priority*                 1                                    

  *\>prioritisedBitRate*       Infinity                             

  *\>logicalChannelGroup*      0                                    

  \>*schedulingRequestId*      0           The scheduling request   
                                           configuration with this  
                                           value is applicable for  
                                           this SCCH if configured  
                                           by the network.          
  ----------------------------------------------------------------------------