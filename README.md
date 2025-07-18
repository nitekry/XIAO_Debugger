## baseline test  
<img width="384" height="512" alt="image" src="https://github.com/user-attachments/assets/1c703ac1-490f-4326-9e85-cd99302c96b0" />  
  
Direct to XIAO nRF sense from mmwave sensor.  


USB Serial output --
<pre>UART TX/RX Echo Started
Sent: Hello World #0
Sent: Hello World #1
Received: $
Received: D
Received: F
Received: H
Received: P
Received: D
Received: ,
Received: 0
Received: ,
Received:
Received: ,
Received:
Received: ,
Received:
Received: * </pre>
</br>

Same test on XIAO Debugger  
  
<img width="384" height="512" alt="image" src="https://github.com/user-attachments/assets/24580d56-8116-4739-98c5-d5c691cff925" />  
  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/638e600b-f987-4a81-982d-4de6a2e6b09c" />  
  
The Debugger window displays the XIAO output on pin6 to the RX window on the debugger.  
  
Nothing to TX window.  

-- Serial Console on the XIAO USB --

<pre>Sent: Hello World #40
Received: $
Received: D
Received: F
Received: H
Received: P
Received: D
Received: ,
Received: 1
Received: ,
Received:  
Received: ,
Received:  
Received: ,
Received:  
Received: *
Received: 

Received: </pre>


-- Serial Console on the Seeed XIAO Debugger --  (Passthrough ?)  
  - Nothing on the debugger or serial console  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/efe9dad9-4443-4fb7-af7c-b117747fe66c" />  
  
-- Plug in USB to XAIO direct.  
  - Debugger begins to display the RX window.  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/274bc534-4a52-47c2-8d16-d53695169715" />

Still no TX from "mmwave TX" on "debugger pin7" in TX window.

  
Summary: 
  - There seems to be some disconnect on the debugger device or code for data from XIAO or sensors to the debugger device.  
  - The debugger passthrough is not working (per my thoughts on its purpose.)  
  - Pin 6 RX on the debugger will display sensor TX even without a XIAO connected. This could lead to misleading test results while debugging.  
      - XIAO pin6 lose connection would still display RX data on degugger.  
      - Code error for XIAO on e.g. wrong pin, would still display RX on the debugger.  
  -note: nothing on debugger from the debugger onboard GROVE connector. maybe it was not designed to be used in that way.
  -note: noticed about a 5 second lag in the RX window of the debugger with serial input.

## New test and observation  

Connected basic TX RX  on two XIAO from nrf to an ESP32-C6  

Confirmed board is recognized  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/10f230b6-8b72-48b1-9d65-27749239c1f1" />  

No RX or TX show.  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/5f4abd71-7ff1-460d-9b1a-f97843dcff63" />  

Plugged in the nRF USB serial and started a new session. RX started showing on the debugger.  
<img width="512" height="384" alt="image" src="https://github.com/user-attachments/assets/d657e439-ee1c-4e83-8659-ad43751776a4" />  

Still no passthrough even when board is confirmed. before or after starting serial on XIAO USB.  










