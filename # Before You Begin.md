# Before You Begin

Complete the following tasks before running an IVP job:

- Submit all installation and customization jobs except the IVP job ($770IVP).  


- Apply the appropriate fixes for each product that you are installing.  
  For instructions, see the Installation System documentation.

- Grant the appropriate authorizations.  
  For more information, see the customization information for the products that you have installed.

If you are not the person who installed the products but are submitting the IVP job, ensure that you have the required authorizations to execute each installed product.

- Complete any additional customization tasks for your installed products or components.

---
## Verify Installation

If your jobs use data sets that are managed by the Storage Management Subsystem (SMS), ensure that the SMS service routine load library (`SYS1.CSSLIB`) is APF-authorized.  
Complete this step regardless of whether `SYS1.CSSLIB` is in your system LNKLST or STEPLIB concatenation.

Use one of the following methods:

- Edit either the EXEC statement in the product job step of the IVP job ($770IVP), or your job card:
  - Change the value of the `REGION` parameter to `0M`.
  - If not already addressed by your site SMF defaults, add the `MEMLIMIT` parameter with an appropriate value for your site and the products that you are installing.

Submit the IVP job ($770IVP).  
The IVP job should complete with condition code 0 unless otherwise indicated by comments in the job.

---
### Important
---
The following temporary objects exist only for the duration of the IVP job:

- Database `BMCIVPDB`
- Table space `BMCIVPDB.BMCIVPTS`
- Table `BMC.BMCIVPTB`
- Table `BMC.BMCIVPT2`
- Index `BMC.BMCIVPIX1`