
# ACPro-RC Test Cart Diagram

```mermaid
flowchart TD
    A[AutoCAL_Lite] -->|USB| B
    B(USB Hub)
    B -->|USB-TCM SCPI| D[Rigol DG103]
    B -->|USB-to-RS232 URC-Protocol| E[Arduino]
    B -->|USB URC-Protocol| F[ACPro-RC]
    B -->|USB-to-RS232 SCPI| G[Keithley Meter]
    D -->|Voltage|F
    D -->|Voltage|G
    F -->|24v Actuator|E
    D -->|Sync Output|E
```

* AutoCAL_Lite interfaces to: `Trip Unit`, `Arduino`, `Rigol`, and `Keithley Multimeter`

* Arduino is used to time trips (delta from sync Rigol sync pulse to Trip Unit Actuator)

# AUTOCAL_LITE STATUS

* Automated and manual calibration routines finalized and stable

* Long Time Trip testing works well
* Short Time Trip testing works well
* Instantanious Trip testing works well
* Ground Fault Trips in progress...

# HARDWARE TODO

* Design circuit to programatically control which phases are enabled to R.C. 



