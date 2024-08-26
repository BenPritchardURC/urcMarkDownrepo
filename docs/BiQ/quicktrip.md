# BiQ Quick Trip Implementation Notes

This document provides factual statements regarding how BreakerIQ deals with the quick trip feature of the AC-PRO-2.  Note that BreakerIQ is referred to as “BiQ” throughout this document.

This document is stored in markdown format, and is part of the `URCMarkdownRepo`.

``` mermaid
graph 
    A{QTD2\nUSB\nConnected\nTo ACPro2?};
    A -->|Yes| B{MsgRspLEDs\nIndiate QT\nis On?};
    B -->|Yes| C{QT_LED=output\nQT_IS_ON=True};
    B -->|No| D{QT_LED=input\nQT_IS_ON=QT_LED};
```

## How Does BiQ Determine if Quick Trip Is On?

* BiQ determines if QT is on using feedback from the trip unit. 
* The feedback comes in two forms: from the URC USB message MsgRspLEDs, and from the I/O pin QT_LED (PORT 02, PIN 05).
* QT_LED can be either an input or an output. When it is an input, its state is read by BiQ. When it is an output, its state is set by BiQ. 
* QT ON indication will be provided when the QT state is ON. * To remain ON, the QT state must be detected as ON for a rolling 5 second period.  


## When Does BiQ send AC-PRO-2 a USB Message commanding QT state?

* ACPro2 version 4.0 and greater support URC message MSG_SET_QT_SWITCH_4, which allows remote setting of QT state.
* There is a 1000hz timer running in BiQ that monitors QT_SW_STATUS (PORT 04, PIN 09). When the status of the pin changes, BiQ will send MSG_SET_QT_SWITCH_4 via USB to the connected trip unit.
* On power-up, we do send a USB message.


## What I/O Lines are involved with the Quick Trip Feature in BiQ?

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

## What URC Messages are involved with QT on the BiQ?

### Feedback from Trip Unit

### Command to Trip Unit

# How does the (factory) Hardware QT Switch Screen work?

# How does the “Quick-Trip (QT) Status” Screen work?

# When does BiQ display the Quick Trip Splash Screen?

# Testing Scenarios

# Miscellaneous, possibly pertinent, facts 

# Description From Joe

(Note: the firmware, and explanations above, should match what Joe is saying here. If something Joe says below contradicts what is shown above, please make a note of it so we can resolve.) 

# Diagram From Joe

(Note: the firmware, and explanations above, should match what Joe is saying here. If something Joe says below contradicts what is shown above, please make a note of it so we can resolve.) 