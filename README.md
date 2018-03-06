# eve-jumps
Provides a mysql table of jumps from system to system in eve online.

download: https://github.com/antihax/eve-jumps/releases/download/1/jumps.zip

## Schema
```
CREATE TABLE `jumps` (
  `toSolarSystemID` int(10) unsigned NOT NULL DEFAULT '0',
  `fromSolarSystemID` int(10) unsigned NOT NULL DEFAULT '0',
  `jumps` tinyint(3) unsigned NOT NULL DEFAULT '0',
  `secureJumps` tinyint(3) unsigned NOT NULL DEFAULT '0',
  PRIMARY KEY (`toSolarSystemID`,`fromSolarSystemID`),
  KEY `fromSolarSystemID` (`fromSolarSystemID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

If secureJumps or jumps = 254, the path is not possible. You can change this to null if you wish.
