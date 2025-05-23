# PARMLIB Check

This consists of two EXEC's:

   PRMCK     - ISPF Edit Command
   PRMCKBAT  - Batch front end to PRMCK by Hartmut Beckmann

PRMCK Edit Command

  This application consists of a REXX Exec with imbedded ISPF Panels.
  To use this you need to copy the exec into a library in your SYSPROC
  or SYSEXEC concatenation.

  Usage is to Edit the desired member of SYS1.PARMLIB and enter the
  command PRMCK.

  Syntax: PRMCK cat sysres -debug -notran

  valid options are:
        ?   - will prompt for catalog and sysres
        cat - is a name that will be used in the master
              catalog lookup (find *custom* below) and
              if not found will be used as the master
              catalog name (enter without quotes).
        sysres is the volser of the system ipl volume
              to be checked when a volser of ****** is
              coded.
        -debug - will turn on tracing
        -help  - display short ispf tutorial
        -nowarn  - will ignore all warnings
        -noerror - will ignore all errors
        -report  - will create a report and put you into browse
                   ** this data set will *not* be deleted when done

  Support for PROGxx member statements
     - LNKLST
     - APF
     - LPA
     - SYSLIB
  Support for LNKLSTxx and LPALSTxx members

  Note that the tutorial panel will be displayed if the member type is
  not recognized.

  Verification is not 100% the same as the system will perform when
  used but it does a fair amount of verification.  Errors and Warnings
  are inserted into the Edit display as non-saveable messages.

PRMCKBAT - Batch Front End

This is code that will inovke the PRMCK exec in batch.

See the BATJCL for a sample JCL to run this exec.
