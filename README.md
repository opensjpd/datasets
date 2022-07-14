### License

These data are public records and are free to use without license or permission. Attribution is appreciated. For details, see [license](LICENSE.md)

### Description

This dataset contains three tables, each as a separate file. Each row corresponds to either:

1. an arrest/criminal citation
1. an incident (which may or may not have a corresponding arrest/citation), or
1. a charge that was filed

See the corresponding tables for more information on fields, foreign keys, etc.
Files contain either Arrest data, Incident data, or Charge data. Files with the `_All` suffix are consolidated files 
that contain all time periods with consistent column names. The time-specific files are as-is as provided by 
SJPD and contain some column name inconsistencies.

### Arrests

The "Arrest" datasets contain entries for SJPD stops ("arrests"). This includes booking, where the subject is 
placed in jail pending arraignment, and also [criminal citations](https://www.shouselaw.com/ca/blog/cite-and-release-california/), 
where the subject is not booked, but rather assigned a court date by the officer and promises to appear. The `CURRENT STATUS` 
field distinguishes between these two types of arrests

| Field | Name | Description|
|------|-------|----|
|AB NO| Arrest/Booking Number | ID Specific to that particular arrest |
|GO NO| General Offense number (a.k.a. incident number or case number) | It begins with `SJYYYY` where `Y` is 4-digit year. If this prefix is stripped off, it leaves the incident number, which can be matched to a row in the "Incidents" table. Not all arrests will have a corresponding incident (especially arrests by warrant).|
|PIN| Person Identification Number | A unique number assigned to each individual arrested by SJPD. Can be matched to rows in the "Incidents" and "Charges" tables|

Due to limitations in their internal Record Management System, not all arrests have the arresting officer listed. This issue is being addressed, 
and recent arrests are more likely to have this field available

### Acknowledgements

This is a mirror of the Kaggle dataset "sjpd-incidents-arrests-charges"
