The **BMCHIST_OBJECT** table stores information about the objects being processed during a job.  
This table has an entry for each object processed by the associated step in the **BMCHIST_STEP** table.
Added new line,,,,,,
---

## Object Timing Information

| Column Name            | Data Type        | Description |
|-----------------------|------------------|-------------|
| JOBNAME               | CHAR(8)          | Name of the job submitted |
| JOBID                 | CHAR(8)          | Job Entry Subsystem (JES) job ID |
| IDENTITY              | BIGINT           | Ties to ROW_IDENTITY in the step table (foreign key) |
| UTILNAME              | CHAR(8)          | Utility executed. Possible values:<br>LOAD+, UNLOAD+, REORG+, LOAD, UNLOAD, REORG, STATS, LOBMASTR, DSNUTILB, COPY, RECOVER, REBUILD, RUNSTATS, NGTDISP, MIXED |
| UTILID                | CHAR(16)         | Utility identifier |
| AUTHID                | CHAR(8)          | USERID of job submitter |
| DBNAME                | VARCHAR(24)      | Database name |
| SPNAME                | VARCHAR(24)      | Tablespace name |
| OBJ_CREATOR           | VARCHAR(128)     | Object creator (table/index) |
| OBJ_NAME              | VARCHAR(128)     | Object name (table, index, or phase) |
| OBJ_TYPE              | CHAR(2)          | Object type:<br>TS (tablespace), TB (table), IX (index), PH (phase) |
| SUB_TYPE              | CHAR(1)          | Catalog type based on object type (e.g., G, L, O, P, R) |
| PART_MASK             | VARCHAR(512)     | Bitmask of parts processed (internal use) |
| PART_COUNT            | INTEGER          | Number of partitions |
| BEG_TSTAMP            | TIMESTAMP(10)    | Start timestamp |
| END_TSTAMP            | TIMESTAMP(10)    | End timestamp |
| ELAPSED               | DECIMAL(9,2)     | Elapsed time (seconds) |
| SOURCE                | CHAR(4)          | Row source:<br>UM, UTIL, SS, PLUS |
| ROWS_PROCESSED        | BIGINT           | Number of rows processed |
| PAGES_PROCESSED       | BIGINT           | Number of pages processed |
| ERROR_REASON          | VARCHAR(24)      | Reason REORG PLUS did not process object |
| ERROR_REASON_CD       | CHAR(8)          | Error code for failure |
| COND_CODE             | SMALLINT         | Indicates success/failure |
| UTILITY_SPECIFICATIONS| VARCHAR(256)     | Internal use |
| SCHEMA_VERSION        | SMALLINT         | Version of stored data |

---

## PART_MASK Examples

| Bitmask        | Meaning |
|----------------|--------|
| 1000 0000      | Part 1 |
| 1100 0000      | Parts 1 and 2 |
| 1000 1000      | Parts 1 and 5 |
| 1111 1111      | Parts 1 through 8 |

> Supports up to 512 bytes, representing up to 4096 partitions.
