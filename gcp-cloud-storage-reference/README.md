# Cloud Storage Bucket Settings Reference

This document provides a reference guide to the configurable settings available when creating or modifying a Google Cloud Storage bucket.

## Storage Classes

|  Class    |   Description                                   
|-----------|-----------------------------------------------------------|
| Standard  | Best For frequently accessed data.                        |
| Nearline  | Best for data accessed less than once a month.            |
| Coldine   | Best for data accessed less than a quarter.               |
| Archive   | Lowest-cost storage for data rarely accessed or archived. |

## Location Types

|  Loocation Type    |   Description                                   
|--------------------|------------------------------------------------------------------|
| Region             | Data stored in a single geograhic location (e.g., us-central1).  |                      
| Dual-region        | Data stored across two specific regions.                         |
| Multi-region       | Data stored across a large geographic area (e.g., United States).|          

## Access Control

| Type           |    Description                                                       |
|----------------|----------------------------------------------------------------------|
| Uniform access | Permissions managed at the bucket level using IAM.                   |
| Fine-grained   | Permissions managed at both the bucket and object level using ACLs.  |

## Versioning 

- Allows keeping multiple versions of an object.
- Helps recover from accidental deletion or overwriting.

## Encryption 

- Default: Google managed encryption keys.
- Optional: Customer managed keys using Cloud KMS (CMEK).

## Lifecycle Rules 

- Automate object transition between storage classes.
- Schedule deletions based on object age or conditions.

## Notes

- Some settings (like loctaion) cannot be changed after creation.
- Most settings can be configured via the Console or `gsutil` CLI.

---

