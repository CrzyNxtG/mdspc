### 4.5.3 Logical Channels

The MAC sublayer provides data transfer services on logical channels. To
accommodate different kinds of data transfer services, multiple types of
logical channels are defined i.e. each supporting transfer of a
particular type of information.

Each logical channel type is defined by what type of information is
transferred.

The MAC sublayer provides the control and traffic channels listed in
Table 4.5.3-1 below.

Table 4.5.3-1: Logical channels provided by MAC.

  -----------------------------------------------------------------------
  Logical channel name          Acronym   Control channel Traffic channel
  ----------------------------- --------- --------------- ---------------
  Broadcast Control Channel     BCCH      X               

  Paging Control Channel        PCCH      X               

  Common Control Channel        CCCH      X               

  Dedicated Control Channel     DCCH      X               

  Dedicated Traffic Channel     DTCH                      X

  MBS Control Channel           MCCH      X               

  MBS Traffic Channel           MTCH                      X

  Sidelink Broadcast Control    SBCCH     X               
  Channel                                                 

  Sidelink Control Channel      SCCH      X               

  Sidelink Traffic Channel      STCH                      X
  -----------------------------------------------------------------------