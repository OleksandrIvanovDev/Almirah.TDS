---
title: Software Requirements Specification
author: put your name here
---

# Overview

This is an example of a software requirements specification for an imagined medical device: a bedside patient monitor that continuously measures the heart rate and the blood oxygen saturation (SpO2) of one patient, raises alarms when a vital sign leaves its configured limits, and forwards the measurements to a central nurse station.

The requirements in this document are the top of the traceability chain of this demo project: architecture items in the Software Architecture Document (sad) link up to these requirements, and software units in the Software Detailed Design (sdd) link up to the architecture items.

# Measurement Requirements

[SRS-001] The software shall acquire the heart rate and the SpO2 value from the patient sensors at least once per second.

[SRS-002] The software shall display the current heart rate and SpO2 value on the bedside screen and shall refresh the displayed values at least once per second.

# Alarm Requirements

[SRS-003] The software shall raise an alarm within 3 seconds after a measured vital sign crosses its configured alarm limit.

[SRS-004] The software shall annunciate an active alarm both visually and audibly; the audible annunciation may be paused for at most 60 seconds but shall not be permanently disabled.

# Data Retention Requirements

[SRS-005] The software shall store the measured vital signs of the last 72 hours as trend data and shall preserve the stored trend data across a power loss.

# Connectivity Requirements

[SRS-006] The software shall forward every measurement and every alarm event to the central nurse station over the hospital network.

[SRS-007] The software shall continue local measurement, display, and alarm annunciation without degradation while the hospital network is unavailable.

# System Integrity Requirements

[SRS-008] The software shall execute a self-test at every start-up and shall not enter the monitoring mode when the self-test fails.

[SRS-009] The software shall record every alarm event, every settings change, and every detected fault in a persistent event log.

[SRS-010] The software shall allow changing the alarm limits only after the user has been authenticated as a clinician.

# Document History

| Revision | Description of changes | Date |
|---|---|---|
| A | Initial version | 2026-07-10 |
