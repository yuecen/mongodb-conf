# Mongodb Chunks Group

Following is the instrustion to balance the chunks among the specific shards by tags.

1.  Stop the balancer
```
sh.stopBalancer()
```

2.  Add the tags to the shards
```
sh.addShardTag("rs03","TAG01")
sh.addShardTag("rs01","TAG01")
```

3.  Tag with range
```
sh.addTagRange("DB.COLLECTIONS",{_id:MinKey},{_id:MaxKey},"TAG01")
```

4.  Restart the balancer
```
sh.startBalancer()
```
