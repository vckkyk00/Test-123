# Specify the Data Collector for an Option Set

On the option set’s panel (see *Panel for a new option set (LGCP1001) in Creating-a-DOMPLEX-option-set*):

1. Expand **Data Collector List**.
2. Expand the parameter section for the Data Collector that you want to edit.

If no data collectors are listed, add one or more new data collectors by performing one of the following:

- Type **I** on the `+` sign  
- Type **R** to replicate an existing one, then overwrite the data collector name  

## Data Collector Fields

### Data Collector SSID
- Specify the SSID of the Data Collector subsystem in DOMPLEX.
- Select the `+` next to the SSID to view and edit parameters.

### Max Number of Concurrent Online Users
- Maximum number of online users allowed simultaneously.
- **Required field**
- Valid range: `1–999`
- Default: `100`

### Max Number of Concurrent Batch Users
- Maximum number of batch users allowed simultaneously.
- **Required field**
- Valid range: `0–999`
- Default: `1`

> **Important**  
> Applies only to:
> - BMC AMI Ops Monitor for Db2  
> - Data Collector  
> - Apptune  
> - SQL Performance  

### WTO Messages Route Code
- Specifies the z/OS WTO routing code (determines console destination).
- **Required field**
- Valid range: `0–16`
- Default: `0`

> The System and SQL Performance products use system defaults.  
> Refer to IBM documentation for routing code definitions.

### WTO Upon User Connection
- Determines if message **BMC24100** is issued when a user connects.
- Values:
  - `Y` = Yes (issue message)
  - `N` = No
- Default: `Y`

### WTO Upon User Connect Termination
- Determines if message **BMC24101** is issued when a user disconnects.
- Values:
  - `Y` = Yes (issue message)
  - `N` = No
- Default: `Y`

### Advisor Variable Data DSN
- Name of the Data Collector’s advisor variable repository.

> **Important**  
> Applies only to:
> - BMC AMI Pool Advisor  
> - Solutions that include Pool Advisor  

### BMC AMI Pool Advisor History DSN
- Name of the Pool Advisor history repository.

> **Important**  
> Applies only to:
> - Pool Advisor  
> - Solutions that include Pool Advisor  

## Final Steps

- Press **Enter** to validate values.  
- If errors occur, refer to *Resolving-validation-errors*.

> **Important**  
> You must recycle the Data Collector for changes to take effect using:
> - `DOMSTOP`
> - `DOMSTART`
> - or `DOMREFRESH`
