# zabbix-hardware
Current features:
- RAM hardware info for Windows through WMI
- CPU hardware info with multiprocessor support for Windows through WMI

## Screenshots
[RAM Latest data](https://raw.githubusercontent.com/nobodysu/zabbix-hardware/master/screenshots/hardware-ram-items.png)

[CPU Latest data](https://raw.githubusercontent.com/nobodysu/zabbix-hardware/master/screenshots/hardware-cpu-items.png)

## Testing
```bash
zabbix_get -s 192.0.2.1 -k hw.ram.discovery[get,"Example host"]
zabbix_get -s 192.0.2.1 -k hw.cpu.discovery[get,"Example host"]
```
Default operation mode. Displays json that server should get, detaches, then waits and sends data with zabbix-sender. `Example host` is your `Host name` field in zabbix.
<br /><br />

```bash
zabbix_get -s 192.0.2.1 -k hw.ram.discovery[getverb,"Example host"]
zabbix_get -s 192.0.2.1 -k hw.cpu.discovery[getverb,"Example host"]
```
Verbose mode. Does not detaches or prints LLD. Lists all items sent to zabbix-sender, also it is possible to see sender output in this mode.
