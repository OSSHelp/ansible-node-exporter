# node-exporter

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/node-exporter/status.svg)](https://drone.osshelp.ru/ansible/node-exporter)

Role for [node_exporer](https://github.com/prometheus/node_exporter) installation and configuration.

## Usage (example)

By default role will disable all possible collectors, so you need to specify at least one collector to enable with `node_exporter_enabled_collectors` array. Example for `supervisord` and `systemd` collectors:

```yaml
    - role: node-exporter
      node_exporter_enabled_collectors:
        - supervisord
        - systemd
```

Supported collectors list with description is available below.

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `node_exporter_setup` | `full` | Setup mode. See [OSSHelp KB article](https://oss.help/kb4895) |
| `node_exporter_enabled_collectors` | `[]` | Array to enable collectors. By default the role disables all. |
| `node_exporter_collect_nvme_metrics` | `false` | If set to `true` - enables textfile collector and places special script for collecting NVMe S.M.A.R.T. metrics with it. |

### Available collectors

List and description of available collectors.

| Collector | Description |
| -------- | -------- |
| `arp` | Exposes ARP statistics from `/proc/net/arp`. |
| `bcache` | Exposes bcache statistics from `/sys/fs/bcache/`. |
| `bonding` | Exposes the number of configured and active slaves of Linux bonding interfaces. |
| `conntrack` | Shows conntrack statistics (does nothing if no `/proc/sys/net/netfilter/` present). |
| `cpu` | Exposes CPU statistics. |
| `cpufreq` | Exposes CPU frequency statistics. |
| `diskstats` | Exposes disk I/O statistics. |
| `edac` | Exposes error detection and correction statistics. |
| `entropy` | Exposes available entropy. |
| `filefd` | Exposes file descriptor statistics from `/proc/sys/fs/file-nr`. |
| `filesystem` | Exposes filesystem statistics, such as disk space used. |
| `hwmon` | Expose hardware monitoring and sensor data from `/sys/class/hwmon/`. |
| `infiniband` | Exposes network statistics specific to InfiniBand and Intel OmniPath configurations. |
| `ipvs` | Exposes IPVS status from `/proc/net/ip_vs` and stats from `/proc/net/ip_vs_stats`. |
| `loadavg` | Exposes load average |
| `mdadm` | Exposes statistics about devices in `/proc/mdstat` (does nothing if no `/proc/mdstat` present). |
| `meminfo` | Exposes memory statistics. |
| `netclass` | Exposes network interface info from `/sys/class/net/`. |
| `netdev` | Exposes network interface statistics such as bytes transferred. |
| `netstat` | Exposes network statistics from `/proc/net/netstat`. This is the same information as `netstat -s`. |
| `nfs` | Exposes NFS client statistics from `/proc/net/rpc/nfs`. This is the same information as `nfsstat -c`. |
| `nfsd` | Exposes NFS kernel server statistics from `/proc/net/rpc/nfsd`. This is the same information as `nfsstat -s`. |
| `pressure` | Exposes pressure stall statistics from `/proc/pressure/`, kernel 4.20+ and/or CONFIG_PSI needed. |
| `rapl` | Exposes various statistics from `/sys/class/powercap`. |
| `schedstat` | Exposes task scheduler statistics from `/proc/schedstat`. |
| `sockstat` | Exposes various statistics from `/proc/net/sockstat`. |
| `softnet` | Exposes statistics from `/proc/net/softnet_stat`. |
| `stat` | Exposes various statistics from `/proc/stat`. This includes boot time, forks and interrupts. |
| `textfile` | Exposes statistics read from local disk. |
| `thermal_zone` | Exposes thermal zone & cooling device statistics from `/sys/class/thermal`. |
| `time` | Exposes the current system time. |
| `timex` | Exposes selected adjtimex(2) system call stats. |
| `udp_queues` | Exposes UDP total lengths of the rx_queue and tx_queue from `/proc/net/udp` and `/proc/net/udp6`. |
| `uname` | Exposes system information as provided by the `uname` system call. |
| `vmstat` | Exposes statistics from `/proc/vmstat`. |
| `xfs` | Exposes XFS runtime statistics (kernel 4.4+ needed). |
| `zfs` | Exposes ZFS performance statistics. |
| `buddyinfo` | Exposes statistics of memory fragments as reported by `/proc/buddyinfo`. |
| `drbd` | Exposes Distributed Replicated Block Device statistics. |
| `interrupts` | Exposes detailed interrupts statistics. |
| `ksmd` | Exposes kernel and system statistics from `/sys/kernel/mm/ksm`. |
| `logind` | Exposes session counts from logind. |
| `meminfo_numa` | Exposes memory statistics from `/proc/meminfo_numa`. |
| `mountstats` | Exposes filesystem statistics from `/proc/self/mountstats`. Exposes detailed NFS client statistics. |
| `ntp` | Exposes local NTP daemon health to check time. |
| `processes` | Exposes aggregate process statistics from `/proc`. |
| `qdisc` | Exposes queuing discipline statistics. |
| `runit` | Exposes service status from runit. |
| `supervisord` | Exposes service status from supervisord. |
| `systemd` | Exposes service and system status from systemd. |
| `tcpstat` | Exposes TCP connection status information from `/proc/net/tcp` and `/proc/net/tcp6`. (Warning: the current version has potential performance issues in high load situations.) |
| `wifi` | Exposes WiFi device and station statistics. |
| `perf` | Exposes perf based metrics (Warning: Metrics are dependent on kernel configuration and settings). |

## FAQ

None, so far.

## Useful links

- [Official documentation](https://github.com/prometheus/node_exporter/blob/master/README.md)

## TODO

- add `textfile` collector support
- optimize tests

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
