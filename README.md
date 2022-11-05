# grafana-zfs

![granfana-zfs-metrics-overview-1](https://user-images.githubusercontent.com/7524620/200136236-8f6e7590-dfd9-41f3-b970-3dc7e2f347e6.jpg)

A dashboard of metrics produced by the `zpool_influxdb` utility. You can read the [manpage](https://openzfs.github.io/openzfs-docs/man/8/zpool_influxdb.8.html) and check out the tool's [GitHub page](https://github.com/richardelling/zpool_influxdb) for more info on what it does and how it works.

Features include pool activity, status, queues, and individual/aggregate IO sizes.

This is a port of [Scott MacDonald's influxQL / v1 dashboard](https://grafana.com/grafana/dashboards/15362-zfs-pool-metrics/). This updated dashboard supports InfluxDBv2 and is written in [flux](https://docs.influxdata.com/influxdb/cloud/reference/syntax/flux/flux-vs-influxql/).

This dahboard is [posted on Grafana's dashboards section](https://grafana.com/grafana/dashboards/17350-zfs-pool-metrics-influxdb-v2/). If you have time, I'd appreciate a rating and review there!
