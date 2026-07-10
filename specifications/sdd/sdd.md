---
title: Software Detailed Design
author: put your name here
---

# Overview

This document refines the modules of the Software Architecture Document (sad) into software units. Every unit links up to the architecture item of the module it belongs to, completing the traceability chain srs to sad to sdd of this demo project.

# Measurement Module Units

[SDD-001] The SensorDriver unit shall read the raw SpO2 and ECG signals from the sensor hardware over the serial interface, time-stamp every reading, and reject readings that fail the plausibility range check. >[SAD-010]

[SDD-002] The SampleProcessor unit shall filter the accepted readings, derive one heart-rate and one SpO2 sample per second, and publish the pair on the internal sample bus. >[SAD-010]

# Display Module Units

[SDD-003] The VitalsView unit shall subscribe to the sample bus and render the numeric heart-rate and SpO2 values, redrawing within 200 milliseconds after a new sample arrives. >[SAD-011]

[SDD-004] The AlarmBanner unit shall render the active alarm state received from the AlarmStateMachine unit as a colored banner with the alarm text on top of every screen. >[SAD-011]

# Alarm Module Units

[SDD-005] The LimitEvaluator unit shall compare every published sample against the configured alarm limits and shall emit a limit-violation event no later than the next evaluation cycle. >[SAD-012]

[SDD-006] The AlarmStateMachine unit shall manage the alarm life cycle (inactive, active, paused-audio) and shall drive the visual annunciator and the audio amplifier, enforcing the 60-second upper bound of the audio pause. >[SAD-012]

# Trend Storage Module Units

[SDD-007] The TrendRingBuffer unit shall append every published sample to a circular file in non-volatile memory sized for 72 hours of data, and shall recover the write position from the file itself after a power loss. >[SAD-013]

# Connectivity Module Units

[SDD-008] The NurseStationClient unit shall serialize samples and alarm events into export messages and deliver them to the nurse station with delivery confirmation. >[SAD-014]

[SDD-009] The OfflineQueue unit shall buffer undelivered export messages while the network is unavailable and shall drain the queue in order after the connection returns, without back-pressure on the sample bus. >[SAD-014]

# System Supervisor Units

[SDD-010] The SelfTestSequencer unit shall execute the start-up self-test steps (memory check, sensor presence, annunciator check) and shall release the monitoring mode only when every step has passed. >[SAD-015]

[SDD-011] The CoreWatchdog unit shall expect a liveness token from the Measurement Module and the Alarm Module every second and shall raise a device fault when a token is missed twice in a row. >[SAD-015]

# Configuration and Audit Module Units

[SDD-012] The AccessController unit shall verify the clinician credentials against the local user store before unlocking the alarm-limit editor, and shall lock it again after 60 seconds of inactivity. >[SAD-016]

[SDD-013] The AuditLogger unit shall append alarm events, settings changes, and detected faults as tamper-evident entries to the persistent event log. >[SAD-016]

# Document History

| Revision | Description of changes | Date |
|---|---|---|
| A | Initial version | 2026-07-10 |
