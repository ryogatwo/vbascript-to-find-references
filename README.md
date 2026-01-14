
   Find where a given table (or any object name) is referenced anywhere in the CURRENT Access DB.
   Output results to a single table in the CURRENT DB:

       zRefScanResults

   This module DOES NOT create any reports and DOES NOT create any new databases.

 OUTPUT TABLE (recreated every run)
   zRefScanResults fields:
     - ID            (AutoNumber PK)
     - SearchTerm    (what you searched for)
     - FoundIn       (Query / Form / Report / Macro / Code / TableDef)
     - ObjectName    (e.g. query name, form name, module name)
     - SubObject     (e.g. control name)
     - PropertyName  (SQL / RecordSource / ControlSource / RowSource / Connect / etc.)
     - MatchContext  (snipped text around the match)

 EXACT-NAME-ONLY MATCHING RULES
   ✔ Matches: [cim-orders_local]
   ✔ Matches: dbo.[cim-orders_local]
   ✔ Matches: cim-orders_local       (ONLY if standalone token)
   ✘ Does NOT match: cim-orders_local_backup
   ✘ Does NOT match: [cim-orders_local_backup]

 IMPORTANT ABOUT NAMES WITH DASHES (-)
   In Access SQL, names with dashes are normally bracketed: [cim-orders_local]
   This scanner matches BOTH bracketed and standalone-token cases.
