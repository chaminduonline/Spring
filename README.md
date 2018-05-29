# Spring

The way Hibernate interprets AUTO generation type has changed starting with Hibernate version 5.0.

When using Hibernate v 4.0 and Generation Type as AUTO, specifically for MySql, Hibernate would choose the IDENTITY strategy (and thus use the AUTO_INCREMENT feature) for generating IDs for the table in question.

Starting with version 5.0 when Generation Type is selected as AUTO, Hibernate uses SequenceStyleGenerator regardless of the database. In case of MySql Hibernate emulates a sequence using a table and is why you are seeing the hibernate_sequence table. MySql doesn't support the standard sequence type natively.
