cloudfeeds-nabu
===============

*This project is currently in sustaining mode as deployed within Rackspace.  For more information on how to support this in sustaining mode please see https://one.rackspace.com/display/cloudfeeds/Cloud+Feeds+Sustaining+Mode+Documentation+Start+Page.*

[Nabu](http://en.wikipedia.org/wiki/Nabu) <a href="http://www.mesopotamia.co.uk/gods/explore/images/nabu_p.gif"><img src="http://www.mesopotamia.co.uk/gods/explore/images/nabu_p.gif" width="5%" height="5%" alt="Nabu"/></a> is the Babylonian god of writing and wisdom, and is the patron of [the scribes, librarians and archivists](http://en.wikipedia.org/wiki/Preservation_%28library_and_archival_science%29#Antecedents). [cloudfeeds-nabu](http://github.com/rackerlabs/cloudfeeds-nabu) is the code repository for the Cloud Feeds Archiving solution. 

The Cloud Feeds Archiving solution deals with archiving cloud events that come through Rackspace Cloud Feeds' system. The whole solution is comprised of multiple sub components:

* [cloudfeeds-ballista](http://github.com/rackerlabs/cloudfeeds-ballista) is the component that is responsible for reading the Cloud Feeds events from our internal Relational Database and throwing them over to Hadoop FS on a daily basis.

* [Usmu](http://www.ancient.eu/article/221/) <a href="http://www.mesopotamia.co.uk/gods/explore/images/isimud_p.gif"><img src="http://www.mesopotamia.co.uk/gods/explore/images/isimud_p.gif" width="5%" height="5%" alt="Usmu"/></a> is the Akkadian messenger god of Ea. He was a two-faced god, representing his coming and going on errands. Here, [usmu](http://github.com/rackerlabs/cloudfeeds-nabu) is the component that reads the exported data of cloudfeeds-ballista and writing it to a partitioned Hive table.

* [Tiamat](http://en.wikipedia.org/wiki/Tiamat)<a href="http://www.mesopotamia.co.uk/gods/explore/images/tiamatsml.gif"><img src="http://www.mesopotamia.co.uk/gods/explore/images/tiamatsml.gif" width="10%" height="10%" alt="Tiamat"/></a> a monster who is the primordial goddess of the ocean.  In the [Dungeon and Dragons mythos](http://en.wikipedia.org/wiki/Tiamat_%28Dungeons_%26_Dragons%29), she is depicted as a multi-headed dragon<a href="http://img1.wikia.nocookie.net/__cb20110923213244/finalfantasy/images/a/a2/Tiamat_Icon.PNG"><img src="http://img1.wikia.nocookie.net/__cb20110923213244/finalfantasy/images/a/a2/Tiamat_Icon.PNG" width="5%" height="5%" alt="Tiamat"/></a>.  Here, Tiamat is the component that reads the Hive table, produces the tenant archive files, and writes these files in the customer's designated Cloud Files container(s).

## How to build
To build this component, we require:
* Gradle version 2.2 or above

### Simple build
```
gradle clean build
```

### Build an RPM
```
gradle clean buildRpm
```
