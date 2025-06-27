Storage Class: dremio-coordinator and dremio-mongodb - io2 - 6000 IOPS - 512 GB
=================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=25.1MiB/s,w=6384KiB/s][r=3219,w=798 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=41: Wed Jun 25 13:38:54 2025
  read: IOPS=4933, BW=38.5MiB/s (40.4MB/s)(6938MiB/180004msec)
    clat (usec): min=332, max=16032, avg=1618.84, stdev=567.50
     lat (usec): min=332, max=16032, avg=1618.90, stdev=567.50
    clat percentiles (usec):
     |  1.00th=[  644],  5.00th=[ 1106], 10.00th=[ 1156], 20.00th=[ 1237],
     | 30.00th=[ 1287], 40.00th=[ 1319], 50.00th=[ 1369], 60.00th=[ 1434],
     | 70.00th=[ 1647], 80.00th=[ 2212], 90.00th=[ 2442], 95.00th=[ 2868],
     | 99.00th=[ 3163], 99.50th=[ 3294], 99.90th=[ 3654], 99.95th=[ 3818],
     | 99.99th=[ 4293]
   bw (  KiB/s): min=21456, max=101904, per=100.00%, avg=39512.65, stdev=1430.03, samples=2872
   iops        : min= 2682, max=12738, avg=4939.08, stdev=178.75, samples=2872
  write: IOPS=1234, BW=9877KiB/s (10.1MB/s)(1736MiB/180004msec); 0 zone resets
    clat (usec): min=3, max=2964, avg= 6.52, stdev=13.24
     lat (usec): min=3, max=2964, avg= 6.62, stdev=13.24
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    5],
     | 30.00th=[    6], 40.00th=[    6], 50.00th=[    6], 60.00th=[    7],
     | 70.00th=[    7], 80.00th=[    8], 90.00th=[    8], 95.00th=[    9],
     | 99.00th=[   14], 99.50th=[   35], 99.90th=[   67], 99.95th=[   78],
     | 99.99th=[  153]
   bw (  KiB/s): min= 3616, max=26672, per=100.00%, avg=9890.50, stdev=390.75, samples=2872
   iops        : min=  452, max= 3334, avg=1236.31, stdev=48.84, samples=2872
  lat (usec)   : 4=0.15%, 10=19.27%, 20=0.46%, 50=0.09%, 100=0.05%
  lat (usec)   : 250=0.01%, 500=0.01%, 750=0.94%, 1000=0.72%
  lat (msec)   : 2=58.62%, 4=19.67%, 10=0.02%, 20=0.01%
  cpu          : usr=0.17%, sys=0.61%, ctx=888330, majf=0, minf=132
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=888000,222245,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=38.5MiB/s (40.4MB/s), 38.5MiB/s-38.5MiB/s (40.4MB/s-40.4MB/s), io=6938MiB (7274MB), run=180004-180004msec
  WRITE: bw=9877KiB/s (10.1MB/s), 9877KiB/s-9877KiB/s (10.1MB/s-10.1MB/s), io=1736MiB (1821MB), run=180004-180004msec

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=527MiB/s,w=132MiB/s][r=67.4k,w=16.8k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=165: Wed Jun 25 13:52:18 2025
  read: IOPS=65.0k, BW=508MiB/s (533MB/s)(89.3GiB/180007msec)
    clat (nsec): min=948, max=15900k, avg=105255.62, stdev=750569.95
     lat (nsec): min=976, max=15900k, avg=105286.34, stdev=750569.78
    clat percentiles (nsec):
     |  1.00th=[   1012],  5.00th=[   1032], 10.00th=[   1048],
     | 20.00th=[   1080], 30.00th=[   1096], 40.00th=[   1128],
     | 50.00th=[   1160], 60.00th=[   1192], 70.00th=[   1240],
     | 80.00th=[   1336], 90.00th=[   1496], 95.00th=[   1752],
     | 99.00th=[5406720], 99.50th=[6520832], 99.90th=[7700480],
     | 99.95th=[8224768], 99.99th=[9764864]
   bw (  KiB/s): min=417936, max=10781040, per=100.00%, avg=599728.97, stdev=74660.59, samples=2492
   iops        : min=52242, max=1347630, avg=74966.12, stdev=9332.57, samples=2492
  write: IOPS=16.3k, BW=127MiB/s (133MB/s)(22.4GiB/180007msec); 0 zone resets
    clat (nsec): min=1831, max=6197.6k, avg=3804.87, stdev=8573.95
     lat (nsec): min=1883, max=6197.7k, avg=3861.76, stdev=8575.09
    clat percentiles (nsec):
     |  1.00th=[ 2992],  5.00th=[ 3024], 10.00th=[ 3056], 20.00th=[ 3120],
     | 30.00th=[ 3184], 40.00th=[ 3248], 50.00th=[ 3344], 60.00th=[ 3504],
     | 70.00th=[ 3664], 80.00th=[ 3952], 90.00th=[ 4832], 95.00th=[ 5344],
     | 99.00th=[ 8512], 99.50th=[17024], 99.90th=[33536], 99.95th=[39680],
     | 99.99th=[58112]
   bw (  KiB/s): min=102160, max=2697376, per=100.00%, avg=150132.56, stdev=18691.60, samples=2492
   iops        : min=12770, max=337172, avg=18766.56, stdev=2336.45, samples=2492
  lat (nsec)   : 1000=0.24%
  lat (usec)   : 2=76.91%, 4=16.61%, 10=3.70%, 20=0.11%, 50=0.19%
  lat (usec)   : 100=0.03%, 250=0.08%, 500=0.14%, 750=0.12%, 1000=0.11%
  lat (msec)   : 2=0.37%, 4=0.34%, 10=1.06%, 20=0.01%
  cpu          : usr=0.71%, sys=2.86%, ctx=375810, majf=0, minf=158
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=11705005,2930025,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=508MiB/s (533MB/s), 508MiB/s-508MiB/s (533MB/s-533MB/s), io=89.3GiB (95.9GB), run=180007-180007msec
  WRITE: bw=127MiB/s (133MB/s), 127MiB/s-127MiB/s (133MB/s-133MB/s), io=22.4GiB (24.0GB), run=180007-180007msec

Storage Class: dremio-zk and dremio-nats and dremio-logs - gp3 - 600 IOPS - 10 GB
=================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=17.0MiB/s,w=4656KiB/s][r=2174,w=582 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Wed Jun 25 14:12:28 2025
  read: IOPS=2492, BW=19.5MiB/s (20.4MB/s)(3505MiB/180002msec)
    clat (usec): min=308, max=21639, avg=3206.21, stdev=871.32
     lat (usec): min=308, max=21639, avg=3206.27, stdev=871.33
    clat percentiles (usec):
     |  1.00th=[ 1582],  5.00th=[ 2147], 10.00th=[ 2343], 20.00th=[ 2573],
     | 30.00th=[ 2671], 40.00th=[ 2769], 50.00th=[ 2999], 60.00th=[ 3294],
     | 70.00th=[ 3589], 80.00th=[ 3949], 90.00th=[ 4359], 95.00th=[ 4752],
     | 99.00th=[ 5669], 99.50th=[ 5997], 99.90th=[ 6718], 99.95th=[ 7046],
     | 99.99th=[ 8848]
   bw (  KiB/s): min=13376, max=71184, per=100.00%, avg=19953.60, stdev=581.98, samples=2872
   iops        : min= 1672, max= 8898, avg=2494.20, stdev=72.75, samples=2872
  write: IOPS=624, BW=4998KiB/s (5118kB/s)(879MiB/180002msec); 0 zone resets
    clat (usec): min=3, max=6717, avg= 7.77, stdev=53.04
     lat (usec): min=3, max=6717, avg= 7.87, stdev=53.04
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    6], 40.00th=[    7], 50.00th=[    7], 60.00th=[    7],
     | 70.00th=[    8], 80.00th=[    8], 90.00th=[    9], 95.00th=[   10],
     | 99.00th=[   15], 99.50th=[   51], 99.90th=[  101], 99.95th=[  123],
     | 99.99th=[ 2868]
   bw (  KiB/s): min= 2048, max=18624, per=100.00%, avg=5001.45, stdev=186.01, samples=2872
   iops        : min=  256, max= 2328, avg=625.18, stdev=23.25, samples=2872
  lat (usec)   : 4=0.24%, 10=18.94%, 20=0.71%, 50=0.05%, 100=0.08%
  lat (usec)   : 250=0.01%, 500=0.11%, 750=0.51%, 1000=0.06%
  lat (msec)   : 2=1.82%, 4=62.74%, 10=14.72%, 20=0.01%, 50=0.01%
  cpu          : usr=0.09%, sys=0.33%, ctx=448918, majf=0, minf=137
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=448686,112465,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=19.5MiB/s (20.4MB/s), 19.5MiB/s-19.5MiB/s (20.4MB/s-20.4MB/s), io=3505MiB (3676MB), run=180002-180002msec
  WRITE: bw=4998KiB/s (5118kB/s), 4998KiB/s-4998KiB/s (5118kB/s-5118kB/s), io=879MiB (921MB), run=180002-180002msec
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [M(1),_(7)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Wed Jun 25 14:16:47 2025
  read: IOPS=13.7k, BW=107MiB/s (113MB/s)(19.1GiB/182246msec)
    clat (nsec): min=1009, max=76651k, avg=458170.21, stdev=3292483.89
     lat (nsec): min=1037, max=76651k, avg=458200.88, stdev=3292483.72
    clat percentiles (nsec):
     |  1.00th=[    1288],  5.00th=[    1352], 10.00th=[    1384],
     | 20.00th=[    1448], 30.00th=[    1496], 40.00th=[    1544],
     | 50.00th=[    1592], 60.00th=[    1656], 70.00th=[    1720],
     | 80.00th=[    1832], 90.00th=[    1976], 95.00th=[    2160],
     | 99.00th=[21889024], 99.50th=[28704768], 99.90th=[37486592],
     | 99.95th=[40108032], 99.99th=[46399488]
   bw (  KiB/s): min=40992, max=1909680, per=100.00%, avg=137968.48, stdev=15938.62, samples=2310
   iops        : min= 5124, max=238710, avg=17246.06, stdev=1992.33, samples=2310
  write: IOPS=3443, BW=26.9MiB/s (28.2MB/s)(4904MiB/182246msec); 0 zone resets
    clat (nsec): min=1810, max=35254k, avg=4628.36, stdev=133304.31
     lat (nsec): min=1888, max=35254k, avg=4685.63, stdev=133304.57
    clat percentiles (nsec):
     |  1.00th=[ 2992],  5.00th=[ 3024], 10.00th=[ 3088], 20.00th=[ 3184],
     | 30.00th=[ 3280], 40.00th=[ 3376], 50.00th=[ 3504], 60.00th=[ 3600],
     | 70.00th=[ 3760], 80.00th=[ 4320], 90.00th=[ 5152], 95.00th=[ 5792],
     | 99.00th=[ 9024], 99.50th=[22400], 99.90th=[50432], 99.95th=[58624],
     | 99.99th=[81408]
   bw (  KiB/s): min= 9712, max=478784, per=100.00%, avg=34596.61, stdev=4009.15, samples=2310
   iops        : min= 1214, max=59848, avg=4324.58, stdev=501.14, samples=2310
  lat (usec)   : 2=73.18%, 4=19.80%, 10=4.48%, 20=0.07%, 50=0.10%
  lat (usec)   : 100=0.02%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.19%, 4=0.21%, 10=0.66%, 20=0.41%, 50=0.86%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.15%, sys=0.77%, ctx=86006, majf=0, minf=176
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2502876,627653,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=107MiB/s (113MB/s), 107MiB/s-107MiB/s (113MB/s-113MB/s), io=19.1GiB (20.5GB), run=182246-182246msec
  WRITE: bw=26.9MiB/s (28.2MB/s), 26.9MiB/s-26.9MiB/s (28.2MB/s-28.2MB/s), io=4904MiB (5142MB), run=182246-182246msec

Storage Class: dremio-opensearch - gp3 - 2000 IOPS - 128 GB
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=18.4MiB/s,w=4912KiB/s][r=2350,w=614 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Wed Jun 25 14:33:10 2025
  read: IOPS=2453, BW=19.2MiB/s (20.1MB/s)(3450MiB/180003msec)
    clat (usec): min=445, max=15375, avg=3257.86, stdev=844.33
     lat (usec): min=445, max=15375, avg=3257.93, stdev=844.33
    clat percentiles (usec):
     |  1.00th=[ 1598],  5.00th=[ 2212], 10.00th=[ 2409], 20.00th=[ 2606],
     | 30.00th=[ 2704], 40.00th=[ 2900], 50.00th=[ 3130], 60.00th=[ 3326],
     | 70.00th=[ 3621], 80.00th=[ 3982], 90.00th=[ 4359], 95.00th=[ 4752],
     | 99.00th=[ 5669], 99.50th=[ 5997], 99.90th=[ 6783], 99.95th=[ 7046],
     | 99.99th=[ 8291]
   bw (  KiB/s): min=13504, max=71968, per=100.00%, avg=19636.95, stdev=557.08, samples=2872
   iops        : min= 1688, max= 8996, avg=2454.62, stdev=69.63, samples=2872
  write: IOPS=614, BW=4916KiB/s (5033kB/s)(864MiB/180003msec); 0 zone resets
    clat (usec): min=3, max=5596, avg= 7.87, stdev=42.58
     lat (usec): min=3, max=5596, avg= 7.97, stdev=42.58
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    6], 40.00th=[    7], 50.00th=[    7], 60.00th=[    8],
     | 70.00th=[    8], 80.00th=[    8], 90.00th=[   10], 95.00th=[   11],
     | 99.00th=[   16], 99.50th=[   52], 99.90th=[   99], 99.95th=[  113],
     | 99.99th=[ 2147]
   bw (  KiB/s): min= 2016, max=18864, per=100.00%, avg=4918.69, stdev=179.77, samples=2872
   iops        : min=  252, max= 2358, avg=614.84, stdev=22.47, samples=2872
  lat (usec)   : 4=0.03%, 10=18.79%, 20=1.07%, 50=0.05%, 100=0.09%
  lat (usec)   : 250=0.01%, 500=0.10%, 750=0.55%, 1000=0.04%
  lat (msec)   : 2=1.59%, 4=62.87%, 10=14.82%, 20=0.01%
  cpu          : usr=0.11%, sys=0.33%, ctx=441828, majf=0, minf=139
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=441571,110601,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=19.2MiB/s (20.1MB/s), 19.2MiB/s-19.2MiB/s (20.1MB/s-20.1MB/s), io=3450MiB (3617MB), run=180003-180003msec
  WRITE: bw=4916KiB/s (5033kB/s), 4916KiB/s-4916KiB/s (5033kB/s-5033kB/s), io=864MiB (906MB), run=180003-180003msec
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=116MiB/s,w=29.8MiB/s][r=14.9k,w=3819 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Wed Jun 25 14:39:24 2025
  read: IOPS=14.9k, BW=116MiB/s (122MB/s)(20.5GiB/180034msec)
    clat (nsec): min=1121, max=69542k, avg=534778.71, stdev=3660959.23
     lat (nsec): min=1159, max=69542k, avg=534809.36, stdev=3660959.02
    clat percentiles (nsec):
     |  1.00th=[    1320],  5.00th=[    1384], 10.00th=[    1416],
     | 20.00th=[    1480], 30.00th=[    1528], 40.00th=[    1576],
     | 50.00th=[    1640], 60.00th=[    1688], 70.00th=[    1768],
     | 80.00th=[    1864], 90.00th=[    2008], 95.00th=[    2224],
     | 99.00th=[25559040], 99.50th=[30801920], 99.90th=[40108032],
     | 99.95th=[43778048], 99.99th=[50069504]
   bw (  KiB/s): min=95232, max=352304, per=100.00%, avg=119326.04, stdev=1760.97, samples=2872
   iops        : min=11904, max=44038, avg=14915.76, stdev=220.12, samples=2872
  write: IOPS=3740, BW=29.2MiB/s (30.6MB/s)(5260MiB/180034msec); 0 zone resets
    clat (nsec): min=1842, max=34194k, avg=4179.85, stdev=92273.48
     lat (nsec): min=1905, max=34194k, avg=4237.01, stdev=92273.67
    clat percentiles (nsec):
     |  1.00th=[ 2992],  5.00th=[ 3056], 10.00th=[ 3120], 20.00th=[ 3184],
     | 30.00th=[ 3248], 40.00th=[ 3312], 50.00th=[ 3408], 60.00th=[ 3504],
     | 70.00th=[ 3632], 80.00th=[ 3888], 90.00th=[ 5088], 95.00th=[ 5600],
     | 99.00th=[ 8160], 99.50th=[23680], 99.90th=[49920], 99.95th=[56064],
     | 99.99th=[76288]
   bw (  KiB/s): min=22000, max=89792, per=100.00%, avg=29935.06, stdev=523.90, samples=2872
   iops        : min= 2750, max=11224, avg=3741.88, stdev=65.49, samples=2872
  lat (usec)   : 2=71.87%, 4=21.96%, 10=3.50%, 20=0.06%, 50=0.11%
  lat (usec)   : 100=0.02%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.15%, 4=0.19%, 10=0.67%, 20=0.44%, 50=1.02%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.16%, sys=0.70%, ctx=84035, majf=0, minf=161
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2683922,673337,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=116MiB/s (122MB/s), 116MiB/s-116MiB/s (122MB/s-122MB/s), io=20.5GiB (22.0GB), run=180034-180034msec
  WRITE: bw=29.2MiB/s (30.6MB/s), 29.2MiB/s-29.2MiB/s (30.6MB/s-30.6MB/s), io=5260MiB (5516MB), run=180034-180034msec


Storage Class: none - emptyDir on r5dn.4xlarge
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=572MiB/s,w=143MiB/s][r=73.3k,w=18.3k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=42: Wed Jun 25 14:54:00 2025
  read: IOPS=68.3k, BW=533MiB/s (559MB/s)(93.7GiB/180001msec)
    clat (usec): min=36, max=526984, avg=113.65, stdev=156.35
     lat (usec): min=36, max=526985, avg=113.72, stdev=156.35
    clat percentiles (usec):
     |  1.00th=[   87],  5.00th=[   90], 10.00th=[   92], 20.00th=[   94],
     | 30.00th=[   97], 40.00th=[  101], 50.00th=[  106], 60.00th=[  110],
     | 70.00th=[  114], 80.00th=[  122], 90.00th=[  145], 95.00th=[  165],
     | 99.00th=[  281], 99.50th=[  322], 99.90th=[  449], 99.95th=[  498],
     | 99.99th=[  701]
   bw (  KiB/s): min=156224, max=604064, per=100.00%, avg=550112.37, stdev=9307.64, samples=2852
   iops        : min=19528, max=75508, avg=68764.06, stdev=1163.45, samples=2852
  write: IOPS=17.1k, BW=133MiB/s (140MB/s)(23.5GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=6056, avg= 5.26, stdev= 8.92
     lat (usec): min=2, max=6056, avg= 5.37, stdev= 8.92
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    4], 10.00th=[    4], 20.00th=[    5],
     | 30.00th=[    5], 40.00th=[    5], 50.00th=[    5], 60.00th=[    6],
     | 70.00th=[    6], 80.00th=[    6], 90.00th=[    7], 95.00th=[    7],
     | 99.00th=[   10], 99.50th=[   29], 99.90th=[   51], 99.95th=[   61],
     | 99.99th=[  105]
   bw (  KiB/s): min=37104, max=161760, per=100.00%, avg=137708.79, stdev=2392.82, samples=2852
   iops        : min= 4638, max=20220, avg=17213.60, stdev=299.10, samples=2852
  lat (usec)   : 4=2.34%, 10=17.49%, 20=0.08%, 50=0.10%, 100=30.45%
  lat (usec)   : 250=48.45%, 500=1.07%, 750=0.03%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 100=0.01%, 750=0.01%
  cpu          : usr=2.03%, sys=9.38%, ctx=12289225, majf=0, minf=131
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=12286354,3075689,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=533MiB/s (559MB/s), 533MiB/s-533MiB/s (559MB/s-559MB/s), io=93.7GiB (101GB), run=180001-180001msec
  WRITE: bw=133MiB/s (140MB/s), 133MiB/s-133MiB/s (140MB/s-140MB/s), io=23.5GiB (25.2GB), run=180001-180001msec
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(3),M(1),_(4)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=147: Wed Jun 25 15:03:48 2025
  read: IOPS=118k, BW=920MiB/s (965MB/s)(166GiB/184910msec)
    clat (nsec): min=951, max=36031k, avg=38077.19, stdev=826895.34
     lat (nsec): min=979, max=36031k, avg=38105.99, stdev=826895.36
    clat percentiles (nsec):
     |  1.00th=[    1080],  5.00th=[    1112], 10.00th=[    1144],
     | 20.00th=[    1176], 30.00th=[    1224], 40.00th=[    1272],
     | 50.00th=[    1336], 60.00th=[    1384], 70.00th=[    1448],
     | 80.00th=[    1544], 90.00th=[    1672], 95.00th=[    1800],
     | 99.00th=[    2640], 99.50th=[    6752], 99.90th=[17956864],
     | 99.95th=[23199744], 99.99th=[25559040]
   bw (  MiB/s): min=  291, max=13823, per=100.00%, avg=1624.74, stdev=229.45, samples=1722
   iops        : min=37280, max=1769462, avg=207967.15, stdev=29369.95, samples=1722
  write: IOPS=29.5k, BW=230MiB/s (241MB/s)(41.5GiB/184910msec); 0 zone resets
    clat (nsec): min=1381, max=1114.4k, avg=3173.03, stdev=2207.98
     lat (nsec): min=1431, max=1114.4k, avg=3225.16, stdev=2210.99
    clat percentiles (nsec):
     |  1.00th=[ 2480],  5.00th=[ 2512], 10.00th=[ 2512], 20.00th=[ 2544],
     | 30.00th=[ 2576], 40.00th=[ 2608], 50.00th=[ 2704], 60.00th=[ 2864],
     | 70.00th=[ 3280], 80.00th=[ 3376], 90.00th=[ 3696], 95.00th=[ 4384],
     | 99.00th=[ 8256], 99.50th=[16768], 99.90th=[33024], 99.95th=[38144],
     | 99.99th=[52992]
   bw (  KiB/s): min=77168, max=3532880, per=100.00%, avg=416355.30, stdev=58574.68, samples=1721
   iops        : min= 9646, max=441610, avg=52044.42, stdev=7321.83, samples=1721
  lat (nsec)   : 1000=0.01%
  lat (usec)   : 2=78.41%, 4=19.12%, 10=1.99%, 20=0.09%, 50=0.08%
  lat (usec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.10%, 4=0.02%, 10=0.04%, 20=0.06%, 50=0.06%
  cpu          : usr=1.19%, sys=3.58%, ctx=263600, majf=0, minf=149
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=21778432,5445612,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=920MiB/s (965MB/s), 920MiB/s-920MiB/s (965MB/s-965MB/s), io=166GiB (178GB), run=184910-184910msec
  WRITE: bw=230MiB/s (241MB/s), 230MiB/s-230MiB/s (241MB/s-241MB/s), io=41.5GiB (44.6GB), run=184910-184910msec


Storage Class: none - emptyDir on m5dn.8xlarge
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=564MiB/s,w=139MiB/s][r=72.2k,w=17.8k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=56: Wed Jun 25 15:12:36 2025
  read: IOPS=68.9k, BW=538MiB/s (564MB/s)(94.6GiB/180001msec)
    clat (usec): min=39, max=418953, avg=112.90, stdev=124.39
     lat (usec): min=40, max=418953, avg=112.97, stdev=124.39
    clat percentiles (usec):
     |  1.00th=[   88],  5.00th=[   91], 10.00th=[   93], 20.00th=[   95],
     | 30.00th=[   99], 40.00th=[  104], 50.00th=[  108], 60.00th=[  110],
     | 70.00th=[  113], 80.00th=[  118], 90.00th=[  139], 95.00th=[  157],
     | 99.00th=[  269], 99.50th=[  363], 99.90th=[  515], 99.95th=[  603],
     | 99.99th=[  775]
   bw (  KiB/s): min=118608, max=593952, per=100.00%, avg=554518.54, stdev=9601.83, samples=2855
   iops        : min=14826, max=74244, avg=69314.81, stdev=1200.23, samples=2855
  write: IOPS=17.2k, BW=135MiB/s (141MB/s)(23.7GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=1414, avg= 4.85, stdev= 3.63
     lat (usec): min=2, max=1414, avg= 4.95, stdev= 3.64
    clat percentiles (nsec):
     |  1.00th=[ 3472],  5.00th=[ 3600], 10.00th=[ 3728], 20.00th=[ 4048],
     | 30.00th=[ 4128], 40.00th=[ 4256], 50.00th=[ 4320], 60.00th=[ 4512],
     | 70.00th=[ 4832], 80.00th=[ 5216], 90.00th=[ 5856], 95.00th=[ 6496],
     | 99.00th=[11200], 99.50th=[25984], 99.90th=[37632], 99.95th=[44800],
     | 99.99th=[95744]
   bw (  KiB/s): min=28464, max=159808, per=100.00%, avg=138819.49, stdev=2478.31, samples=2855
   iops        : min= 3558, max=19976, avg=17352.44, stdev=309.79, samples=2855
  lat (usec)   : 4=3.34%, 10=16.45%, 20=0.06%, 50=0.16%, 100=26.82%
  lat (usec)   : 250=52.25%, 500=0.82%, 750=0.09%, 1000=0.01%
  lat (msec)   : 2=0.01%, 500=0.01%
  cpu          : usr=2.02%, sys=9.17%, ctx=12465609, majf=0, minf=123
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=12398569,3103667,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=538MiB/s (564MB/s), 538MiB/s-538MiB/s (564MB/s-564MB/s), io=94.6GiB (102GB), run=180001-180001msec
  WRITE: bw=135MiB/s (141MB/s), 135MiB/s-135MiB/s (141MB/s-141MB/s), io=23.7GiB (25.4GB), run=180001-180001msec

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(2),M(1),_(5)][100.0%][r=8KiB/s][r=1 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=98: Wed Jun 25 15:16:41 2025
  read: IOPS=276k, BW=2157MiB/s (2262MB/s)(391GiB/185787msec)
    clat (nsec): min=1013, max=32935k, avg=16646.69, stdev=346485.40
     lat (nsec): min=1040, max=32935k, avg=16675.17, stdev=346485.39
    clat percentiles (nsec):
     |  1.00th=[    1288],  5.00th=[    1320], 10.00th=[    1352],
     | 20.00th=[    1368], 30.00th=[    1384], 40.00th=[    1400],
     | 50.00th=[    1432], 60.00th=[    1480], 70.00th=[    1544],
     | 80.00th=[    1672], 90.00th=[    1864], 95.00th=[    1976],
     | 99.00th=[    2384], 99.50th=[    5536], 99.90th=[ 6258688],
     | 99.95th=[ 9371648], 99.99th=[13303808]
   bw (  MiB/s): min=  370, max=20892, per=100.00%, avg=3423.38, stdev=333.75, samples=1869
   iops        : min=47382, max=2674250, avg=438192.56, stdev=42719.81, samples=1869
  write: IOPS=69.0k, BW=539MiB/s (565MB/s)(97.8GiB/185787msec); 0 zone resets
    clat (nsec): min=1378, max=5772.2k, avg=3240.26, stdev=2437.56
     lat (nsec): min=1430, max=5772.2k, avg=3291.50, stdev=2439.20
    clat percentiles (nsec):
     |  1.00th=[ 2480],  5.00th=[ 2512], 10.00th=[ 2512], 20.00th=[ 2544],
     | 30.00th=[ 2576], 40.00th=[ 2672], 50.00th=[ 2800], 60.00th=[ 3248],
     | 70.00th=[ 3312], 80.00th=[ 3408], 90.00th=[ 3952], 95.00th=[ 4512],
     | 99.00th=[11328], 99.50th=[15808], 99.90th=[22144], 99.95th=[25216],
     | 99.99th=[36608]
   bw (  KiB/s): min=95136, max=5345216, per=100.00%, avg=876409.96, stdev=85284.89, samples=1869
   iops        : min=11892, max=668152, avg=109551.24, stdev=10660.61, samples=1869
  lat (usec)   : 2=76.54%, 4=20.82%, 10=2.10%, 20=0.21%, 50=0.04%
  lat (usec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.07%, 4=0.05%, 10=0.08%, 20=0.04%, 50=0.01%
  cpu          : usr=2.64%, sys=10.08%, ctx=623257, majf=0, minf=157
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=51291627,12823314,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=2157MiB/s (2262MB/s), 2157MiB/s-2157MiB/s (2262MB/s-2262MB/s), io=391GiB (420GB), run=185787-185787msec
  WRITE: bw=539MiB/s (565MB/s), 539MiB/s-539MiB/s (565MB/s-565MB/s), io=97.8GiB (105GB), run=185787-185787msec

Storage Class: dremio-gp2 - gp2 - 50 GB (AWSE coordinator disk)
===============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=17.6MiB/s,w=4488KiB/s][r=2248,w=561 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=41: Fri Jun 27 08:56:05 2025
  read: IOPS=2467, BW=19.3MiB/s (20.2MB/s)(3470MiB/180004msec)
    clat (usec): min=315, max=110508, avg=3239.11, stdev=1018.48
     lat (usec): min=315, max=110508, avg=3239.18, stdev=1018.48
    clat percentiles (usec):
     |  1.00th=[  906],  5.00th=[ 2311], 10.00th=[ 2507], 20.00th=[ 2638],
     | 30.00th=[ 2704], 40.00th=[ 2868], 50.00th=[ 3064], 60.00th=[ 3294],
     | 70.00th=[ 3556], 80.00th=[ 3949], 90.00th=[ 4293], 95.00th=[ 4686],
     | 99.00th=[ 5604], 99.50th=[ 5866], 99.90th=[ 6456], 99.95th=[ 6915],
     | 99.99th=[ 7504]
   bw (  KiB/s): min=13376, max=71952, per=100.00%, avg=19746.32, stdev=547.32, samples=2872
   iops        : min= 1672, max= 8994, avg=2468.29, stdev=68.41, samples=2872
  write: IOPS=618, BW=4945KiB/s (5064kB/s)(869MiB/180004msec); 0 zone resets
    clat (usec): min=3, max=4395, avg= 7.86, stdev=35.39
     lat (usec): min=3, max=4395, avg= 7.96, stdev=35.39
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    7], 40.00th=[    7], 50.00th=[    7], 60.00th=[    8],
     | 70.00th=[    8], 80.00th=[    9], 90.00th=[   10], 95.00th=[   11],
     | 99.00th=[   16], 99.50th=[   48], 99.90th=[   76], 99.95th=[   99],
     | 99.99th=[ 2114]
   bw (  KiB/s): min= 2032, max=18928, per=100.00%, avg=4948.72, stdev=179.10, samples=2872
   iops        : min=  254, max= 2366, avg=618.59, stdev=22.39, samples=2872
  lat (usec)   : 4=0.02%, 10=18.83%, 20=1.03%, 50=0.06%, 100=0.09%
  lat (usec)   : 250=0.01%, 500=0.01%, 750=0.71%, 1000=0.10%
  lat (msec)   : 2=0.98%, 4=64.07%, 10=14.09%, 20=0.01%, 250=0.01%
  cpu          : usr=0.08%, sys=0.37%, ctx=444383, majf=0, minf=126
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=444134,111271,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=19.3MiB/s (20.2MB/s), 19.3MiB/s-19.3MiB/s (20.2MB/s-20.2MB/s), io=3470MiB (3638MB), run=180004-180004msec
  WRITE: bw=4945KiB/s (5064kB/s), 4945KiB/s-4945KiB/s (5064kB/s-5064kB/s), io=869MiB (912MB), run=180004-180004msec

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Starting 8 processes
Jobs: 1 (f=1): [_(7),M(1)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=68: Fri Jun 27 09:03:44 2025
  read: IOPS=14.0k, BW=109MiB/s (115MB/s)(19.6GiB/183917msec)
    clat (nsec): min=1012, max=68817k, avg=415222.53, stdev=3121083.89
     lat (nsec): min=1041, max=68817k, avg=415252.94, stdev=3121083.71
    clat percentiles (nsec):
     |  1.00th=[    1336],  5.00th=[    1464], 10.00th=[    1528],
     | 20.00th=[    1592], 30.00th=[    1640], 40.00th=[    1688],
     | 50.00th=[    1752], 60.00th=[    1816], 70.00th=[    1896],
     | 80.00th=[    1992], 90.00th=[    2128], 95.00th=[    2288],
     | 99.00th=[19005440], 99.50th=[28442624], 99.90th=[36962304],
     | 99.95th=[40632320], 99.99th=[46399488]
   bw (  KiB/s): min=44032, max=2073424, per=100.00%, avg=151775.95, stdev=19973.68, samples=2157
   iops        : min= 5504, max=259178, avg=18971.99, stdev=2496.71, samples=2157
  write: IOPS=3508, BW=27.4MiB/s (28.7MB/s)(5042MiB/183917msec); 0 zone resets
    clat (nsec): min=1828, max=33893k, avg=4585.23, stdev=94216.43
     lat (nsec): min=1880, max=33893k, avg=4645.03, stdev=94216.62
    clat percentiles (nsec):
     |  1.00th=[ 3056],  5.00th=[ 3248], 10.00th=[ 3344], 20.00th=[ 3440],
     | 30.00th=[ 3536], 40.00th=[ 3632], 50.00th=[ 3760], 60.00th=[ 3856],
     | 70.00th=[ 4016], 80.00th=[ 4448], 90.00th=[ 5472], 95.00th=[ 6112],
     | 99.00th=[ 9408], 99.50th=[22400], 99.90th=[44800], 99.95th=[50944],
     | 99.99th=[66048]
   bw (  KiB/s): min=10976, max=520496, per=100.00%, avg=38046.63, stdev=5031.41, samples=2157
   iops        : min= 1372, max=65062, avg=4755.83, stdev=628.93, samples=2157
  lat (usec)   : 2=65.01%, 4=26.27%, 10=6.16%, 20=0.09%, 50=0.11%
  lat (usec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.31%, 4=0.27%, 10=0.64%, 20=0.34%, 50=0.76%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.17%, sys=0.81%, ctx=88419, majf=0, minf=172
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2574665,645332,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=109MiB/s (115MB/s), 109MiB/s-109MiB/s (115MB/s-115MB/s), io=19.6GiB (21.1GB), run=183917-183917msec
  WRITE: bw=27.4MiB/s (28.7MB/s), 27.4MiB/s-27.4MiB/s (28.7MB/s-28.7MB/s), io=5042MiB (5287MB), run=183917-183917msecs

Storage Class: dremio-gp3 - gp3 (default IOPS) - 50 GB
======================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
kvstore_test: Laying out IO file (1 file / 1024MiB)
Jobs: 8 (f=8): [m(8)][100.0%][r=20.9MiB/s,w=5013KiB/s][r=2670,w=626 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Fri Jun 27 09:11:58 2025
  read: IOPS=2564, BW=20.0MiB/s (21.0MB/s)(3607MiB/180003msec)
    clat (usec): min=471, max=10594, avg=3116.18, stdev=569.46
     lat (usec): min=471, max=10594, avg=3116.25, stdev=569.46
    clat percentiles (usec):
     |  1.00th=[ 1860],  5.00th=[ 2474], 10.00th=[ 2638], 20.00th=[ 2737],
     | 30.00th=[ 2933], 40.00th=[ 2966], 50.00th=[ 2999], 60.00th=[ 3064],
     | 70.00th=[ 3261], 80.00th=[ 3359], 90.00th=[ 3949], 95.00th=[ 4080],
     | 99.00th=[ 4883], 99.50th=[ 5342], 99.90th=[ 5800], 99.95th=[ 6063],
     | 99.99th=[ 6718]
   bw (  KiB/s): min=14224, max=71024, per=100.00%, avg=20521.72, stdev=442.19, samples=2872
   iops        : min= 1778, max= 8878, avg=2565.21, stdev=55.27, samples=2872
  write: IOPS=642, BW=5142KiB/s (5265kB/s)(904MiB/180003msec); 0 zone resets
    clat (usec): min=3, max=5683, avg= 7.97, stdev=43.67
     lat (usec): min=3, max=5683, avg= 8.08, stdev=43.67
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    7], 40.00th=[    7], 50.00th=[    7], 60.00th=[    8],
     | 70.00th=[    8], 80.00th=[    9], 90.00th=[   10], 95.00th=[   11],
     | 99.00th=[   16], 99.50th=[   46], 99.90th=[   79], 99.95th=[  112],
     | 99.99th=[ 2671]
   bw (  KiB/s): min= 2288, max=18608, per=100.00%, avg=5142.86, stdev=161.19, samples=2872
   iops        : min=  286, max= 2326, avg=642.85, stdev=20.15, samples=2872
  lat (usec)   : 4=0.02%, 10=18.85%, 20=1.02%, 50=0.06%, 100=0.08%
  lat (usec)   : 250=0.01%, 500=0.01%, 750=0.51%, 1000=0.18%
  lat (msec)   : 2=0.41%, 4=72.57%, 10=6.30%, 20=0.01%
  cpu          : usr=0.09%, sys=0.37%, ctx=461834, majf=0, minf=133
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=461641,115688,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=20.0MiB/s (21.0MB/s), 20.0MiB/s-20.0MiB/s (21.0MB/s-21.0MB/s), io=3607MiB (3782MB), run=180003-180003msec
  WRITE: bw=5142KiB/s (5265kB/s), 5142KiB/s-5142KiB/s (5265kB/s-5265kB/s), io=904MiB (948MB), run=180003-180003msec

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(2),M(1),_(5)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=67: Fri Jun 27 09:16:58 2025
  read: IOPS=13.5k, BW=106MiB/s (111MB/s)(18.8GiB/182145msec)
    clat (nsec): min=1041, max=79201k, avg=455133.66, stdev=3316456.05
     lat (nsec): min=1069, max=79201k, avg=455164.41, stdev=3316455.86
    clat percentiles (nsec):
     |  1.00th=[    1368],  5.00th=[    1512], 10.00th=[    1592],
     | 20.00th=[    1672], 30.00th=[    1736], 40.00th=[    1784],
     | 50.00th=[    1848], 60.00th=[    1912], 70.00th=[    1976],
     | 80.00th=[    2064], 90.00th=[    2192], 95.00th=[    2384],
     | 99.00th=[21889024], 99.50th=[29753344], 99.90th=[38010880],
     | 99.95th=[41680896], 99.99th=[45350912]
   bw (  KiB/s): min=30976, max=1798480, per=100.00%, avg=139381.32, stdev=15618.19, samples=2261
   iops        : min= 3872, max=224810, avg=17422.67, stdev=1952.27, samples=2261
  write: IOPS=3385, BW=26.4MiB/s (27.7MB/s)(4818MiB/182145msec); 0 zone resets
    clat (nsec): min=1800, max=36614k, avg=4834.27, stdev=107147.41
     lat (nsec): min=1851, max=36614k, avg=4893.43, stdev=107147.62
    clat percentiles (nsec):
     |  1.00th=[ 3120],  5.00th=[ 3376], 10.00th=[ 3504], 20.00th=[ 3600],
     | 30.00th=[ 3696], 40.00th=[ 3792], 50.00th=[ 3888], 60.00th=[ 4016],
     | 70.00th=[ 4192], 80.00th=[ 4640], 90.00th=[ 5792], 95.00th=[ 6432],
     | 99.00th=[10048], 99.50th=[24192], 99.90th=[47872], 99.95th=[54016],
     | 99.99th=[72192]
   bw (  KiB/s): min= 8048, max=446832, per=100.00%, avg=34926.34, stdev=3901.98, samples=2261
   iops        : min= 1006, max=55854, avg=4365.79, stdev=487.75, samples=2261
  lat (usec)   : 2=57.69%, 4=31.80%, 10=7.89%, 20=0.11%, 50=0.11%
  lat (usec)   : 100=0.02%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.28%, 4=0.22%, 10=0.67%, 20=0.34%, 50=0.86%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.16%, sys=0.83%, ctx=85995, majf=0, minf=163
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2461132,616667,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=106MiB/s (111MB/s), 106MiB/s-106MiB/s (111MB/s-111MB/s), io=18.8GiB (20.2GB), run=182145-182145msec
  WRITE: bw=26.4MiB/s (27.7MB/s), 26.4MiB/s-26.4MiB/s (27.7MB/s-27.7MB/s), io=4818MiB (5052MB), run=182145-182145msec