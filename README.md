# grafana-zfs-metrics

![granfana-zfs-metrics-overview-1](https://user-images.githubusercontent.com/7524620/200136236-8f6e7590-dfd9-41f3-b970-3dc7e2f347e6.jpg)

A dashboard of metrics produced by the `zpool_influxdb` utility. You can read the [manpage](https://openzfs.github.io/openzfs-docs/man/8/zpool_influxdb.8.html) and check out the tool's [GitHub page](https://github.com/richardelling/zpool_influxdb) for more info on what it does and how it works.

Features include pool activity, status, queues, and individual/aggregate IO sizes.

This is a port of [Scott MacDonald's influxQL / v1 dashboard](https://grafana.com/grafana/dashboards/15362-zfs-pool-metrics/). This updated dashboard supports InfluxDBv2 and is written in [flux](https://docs.influxdata.com/influxdb/cloud/reference/syntax/flux/flux-vs-influxql/).

This dahboard is [posted on Grafana's dashboards section](https://grafana.com/grafana/dashboards/17350-zfs-pool-metrics-influxdb-v2/). If you have time, I'd appreciate a rating and review there!

## Configuration

This uses Telegraf with the  `zpool_influxdb` collector. A [detailed setup guide can be found over at the du.nkel.dev blog](https://du.nkel.dev/blog/2021-05-05_proxmox_influxdb/), but a simple minimal config is:

```
#  Read metrics from zpool_influxdb
[[inputs.exec]]
  # CHECK PATH! Default installation location for zpool_influxdb command may be elsewhere
  commands = ["/usr/lib/zfs-linux/zpool_influxdb"]
  timeout = "5s"
```
## Porting Details

If you're interested in how this was ported from influxQL to flux, I have a series of posts over on my blog on the motivation and process: [Part 1](https://blog.roberthallam.org/2022/09/monitoring-zfs-latencies-in-proxmox-part-1/), [Part 2](https://blog.roberthallam.org/2022/09/monitoring-zfs-with-influxdb-grafana-graph-time-part-2/), [Part 3](https://blog.roberthallam.org/2022/09/monitoring-zfs-with-influxdb-grafana-adapting-panels-part-3/), [Part 4](https://blog.roberthallam.org/2022/09/monitoring-zfs-with-influxdb-grafana-tidying-up-part-4/), [Part 5](https://blog.roberthallam.org/2022/09/monitoring-zfs-with-influxdb-grafana-publishing-and-reflection-part-5/).
