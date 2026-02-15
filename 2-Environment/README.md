# Lab Architecture

## Overview
This investigation was performed in a controlled lab environment designed to simulate a real corporate endpoint monitored by a Security Operations Center (SOC).

The objective was to generate realistic endpoint telemetry and analyze it using Microsoft Defender for Endpoint.

---

## Environment Components

| Component | Purpose |
|--------|------|
Windows Virtual Machine | Simulated corporate employee workstation
Microsoft Defender for Endpoint | Endpoint detection and telemetry collection
Advanced Hunting (KQL) | Threat investigation and log analysis
PowerShell Script | Simulated insider data theft activity

---

## Monitoring Flow

1. User activity occurs on endpoint
2. Microsoft Defender for Endpoint collects telemetry
3. Logs are sent to the security portal
4. Threat hunting queries analyze behavior
5. Incident decision is made

---

## Data Sources Used

The following MDE tables were analyzed:

| Table | Description |
|------|------|
DeviceProcessEvents | Process execution activity
DeviceFileEvents | File creation and modification
DeviceNetworkEvents | Outbound connections

---

## Investigation Model

This lab follows a real SOC investigation methodology:

Detection → Validation → Correlation → Impact Assessment → Response

---

## Goal of the Lab
The goal was not to detect malware, but to identify suspicious user behavior that could indicate insider data theft.

This reflects real enterprise environments where threats often originate from legitimate users rather than external attackers.
