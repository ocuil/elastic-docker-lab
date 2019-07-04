# Elastic 7.2 Docker Lab
Elastic 7.2 with Zookeeper, Kafka and Monitoring cluster

This repo let you deploy a little lab of a fully functionally cluster of elastic with kafka 
I use that to fast deploy a little poc of a functionality or for a demo purpose

- - -

Please check the ip addressing and passwords (by default elastic/elastic)

After deploy...
```bash
#Enable trial
curl -XPOST 172.16.100.20:9200/_xpack/license/start_trial?acknowledge=true && curl -XPOST 172.16.100.23:9200/_xpack/license/start_trial?acknowledge=true

#Setup users password (by default the config files use elastic as password too
docker exec -t -i es1 bin/elasticsearch-setup-passwords interactive && docker exec -t -i esm1 bin/elasticsearch-setup-passwords interactive

#You can use the DEV TOOL to enable de monitoring feature
PUT _cluster/settings
{
  "persistent": {
    "xpack.monitoring.collection.enabled": true
  }
}

```

