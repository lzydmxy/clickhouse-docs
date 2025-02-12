---
sidebar_position: 90
sidebar_label: Security Changelog
---

# Security Changelog

## Fixed in ClickHouse 21.10.2.15, 2021-10-18 {#fixed-in-clickhouse-release-21-10-2-215-2021-10-18}

### CVE-2021-43304 {#cve-2021-43304}

Heap buffer overflow in Clickhouse's LZ4 compression codec when parsing a malicious query. There is no verification that the copy operations in the LZ4::decompressImpl loop and especially the arbitrary copy operation wildCopy<copy_amount>(op, ip, copy_end), don’t exceed the destination buffer’s limits.

Credits: JFrog Security Research Team

### CVE-2021-43305 {#cve-2021-43305}

Heap buffer overflow in Clickhouse's LZ4 compression codec when parsing a malicious query. There is no verification that the copy operations in the LZ4::decompressImpl loop and especially the arbitrary copy operation wildCopy<copy_amount>(op, ip, copy_end), don’t exceed the destination buffer’s limits. This issue is very similar to CVE-2021-43304, but the vulnerable copy operation is in a different wildCopy call.

Credits: JFrog Security Research Team

### CVE-2021-42387 {#cve-2021-42387}

Heap out-of-bounds read in Clickhouse's LZ4 compression codec when parsing a malicious query. As part of the LZ4::decompressImpl() loop, a 16-bit unsigned user-supplied value ('offset') is read from the compressed data. The offset is later used in the length of a copy operation, without checking the upper bounds of the source of the copy operation.

Credits: JFrog Security Research Team

### CVE-2021-42388 {#cve-2021-42388}

Heap out-of-bounds read in Clickhouse's LZ4 compression codec when parsing a malicious query. As part of the LZ4::decompressImpl() loop, a 16-bit unsigned user-supplied value ('offset') is read from the compressed data. The offset is later used in the length of a copy operation, without checking the lower bounds of the source of the copy operation.

Credits: JFrog Security Research Team

### CVE-2021-42389 {#cve-2021-42389}

Divide-by-zero in Clickhouse's Delta compression codec when parsing a malicious query. The first byte of the compressed buffer is used in a modulo operation without being checked for 0.

Credits: JFrog Security Research Team

### CVE-2021-42390 {#cve-2021-42390}

Divide-by-zero in Clickhouse's DeltaDouble compression codec when parsing a malicious query. The first byte of the compressed buffer is used in a modulo operation without being checked for 0.

Credits: JFrog Security Research Team

### CVE-2021-42391 {#cve-2021-42391}

Divide-by-zero in Clickhouse's Gorilla compression codec when parsing a malicious query. The first byte of the compressed buffer is used in a modulo operation without being checked for 0.

Credits: JFrog Security Research Team

## Fixed in ClickHouse 21.4.3.21, 2021-04-12 {#fixed-in-clickhouse-release-21-4-3-21-2021-04-12}

### CVE-2021-25263 {#cve-2021-25263}

An attacker that has CREATE DICTIONARY privilege, can read arbitary file outside permitted directory.

Fix has been pushed to versions 20.8.18.32-lts, 21.1.9.41-stable, 21.2.9.41-stable, 21.3.6.55-lts, 21.4.3.21-stable and later.

Credits: [Vyacheslav Egoshin](https://twitter.com/vegoshin)

## Fixed in ClickHouse Release 19.14.3.3, 2019-09-10 {#fixed-in-clickhouse-release-19-14-3-3-2019-09-10}

### CVE-2019-15024 {#cve-2019-15024}

Аn attacker that has write access to ZooKeeper and who can run a custom server available from the network where ClickHouse runs, can create a custom-built malicious server that will act as a ClickHouse replica and register it in ZooKeeper. When another replica will fetch data part from the malicious replica, it can force clickhouse-server to write to arbitrary path on filesystem.

Credits: Eldar Zaitov of Yandex Information Security Team

### CVE-2019-16535 {#cve-2019-16535}

Аn OOB read, OOB write and integer underflow in decompression algorithms can be used to achieve RCE or DoS via native protocol.

Credits: Eldar Zaitov of Yandex Information Security Team

### CVE-2019-16536 {#cve-2019-16536}

Stack overflow leading to DoS can be triggered by a malicious authenticated client.

Credits: Eldar Zaitov of Yandex Information Security Team

## Fixed in ClickHouse Release 19.13.6.1, 2019-09-20 {#fixed-in-clickhouse-release-19-13-6-1-2019-09-20}

### CVE-2019-18657 {#cve-2019-18657}

Table function `url` had the vulnerability allowed the attacker to inject arbitrary HTTP headers in the request.

Credits: [Nikita Tikhomirov](https://github.com/NSTikhomirov)

## Fixed in ClickHouse Release 18.12.13, 2018-09-10 {#fixed-in-clickhouse-release-18-12-13-2018-09-10}

### CVE-2018-14672 {#cve-2018-14672}

Functions for loading CatBoost models allowed path traversal and reading arbitrary files through error messages.

Credits: Andrey Krasichkov of Yandex Information Security Team

## Fixed in ClickHouse Release 18.10.3, 2018-08-13 {#fixed-in-clickhouse-release-18-10-3-2018-08-13}

### CVE-2018-14671 {#cve-2018-14671}

unixODBC allowed loading arbitrary shared objects from the file system which led to a Remote Code Execution vulnerability.

Credits: Andrey Krasichkov and Evgeny Sidorov of Yandex Information Security Team

## Fixed in ClickHouse Release 1.1.54388, 2018-06-28 {#fixed-in-clickhouse-release-1-1-54388-2018-06-28}

### CVE-2018-14668 {#cve-2018-14668}

“remote” table function allowed arbitrary symbols in “user”, “password” and “default_database” fields which led to Cross Protocol Request Forgery Attacks.

Credits: Andrey Krasichkov of Yandex Information Security Team

## Fixed in ClickHouse Release 1.1.54390, 2018-07-06 {#fixed-in-clickhouse-release-1-1-54390-2018-07-06}

### CVE-2018-14669 {#cve-2018-14669}

ClickHouse MySQL client had “LOAD DATA LOCAL INFILE” functionality enabled that allowed a malicious MySQL database read arbitrary files from the connected ClickHouse server.

Credits: Andrey Krasichkov and Evgeny Sidorov of Yandex Information Security Team

## Fixed in ClickHouse Release 1.1.54131, 2017-01-10 {#fixed-in-clickhouse-release-1-1-54131-2017-01-10}

### CVE-2018-14670 {#cve-2018-14670}

Incorrect configuration in deb package could lead to the unauthorized use of the database.

Credits: the UK’s National Cyber Security Centre (NCSC)

