# CloudStatus

# see:   https://community.cloudera.com/t5/Community-Articles/Using-Cloudera-Flow-Management-To-Ingest-and-Process-RSS/ta-p/313074

![](https://community.cloudera.com/t5/image/serverpage/image-id/30674i50109D5B300D2ED7/image-size/large?v=1.0&px=999)

![](https://community.cloudera.com/t5/image/serverpage/image-id/30676iA30E1269AD551E25/image-size/large?v=1.0&px=999)


# table

CREATE TABLE cloudstatus ( 
   `uuid` STRING,
	`ts` TIMESTAMP,  
	`companyname` STRING,
	`servicename` STRING,
`title` STRING, 
	`description` STRING, 
`pubdate` STRING, 
  `link` STRING,
  `guid` STRING,
PRIMARY KEY (`uuid`,`ts` ) )
PARTITION BY HASH PARTITIONS 4 
STORED AS KUDU TBLPROPERTIES ('kudu.num_tablet_replicas' = '1');

