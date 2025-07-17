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

Storage Class: dremio-zk and dremio-nats and dremio-logs - gp3 - default IOPS - 10 GB
=====================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=15.4MiB/s,w=3859KiB/s][r=1975,w=482 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Fri Jun 27 09:27:38 2025
  read: IOPS=2455, BW=19.2MiB/s (20.1MB/s)(3453MiB/180005msec)
    clat (usec): min=313, max=12698, avg=3254.69, stdev=843.77
     lat (usec): min=313, max=12698, avg=3254.75, stdev=843.77
    clat percentiles (usec):
     |  1.00th=[ 1598],  5.00th=[ 2278], 10.00th=[ 2507], 20.00th=[ 2638],
     | 30.00th=[ 2671], 40.00th=[ 2769], 50.00th=[ 3064], 60.00th=[ 3326],
     | 70.00th=[ 3621], 80.00th=[ 3982], 90.00th=[ 4424], 95.00th=[ 4686],
     | 99.00th=[ 5669], 99.50th=[ 5997], 99.90th=[ 6652], 99.95th=[ 6980],
     | 99.99th=[ 7570]
   bw (  KiB/s): min=13552, max=71200, per=100.00%, avg=19661.06, stdev=566.37, samples=2872
   iops        : min= 1694, max= 8900, avg=2457.63, stdev=70.80, samples=2872
  write: IOPS=615, BW=4921KiB/s (5039kB/s)(865MiB/180005msec); 0 zone resets
    clat (usec): min=3, max=5047, avg= 8.45, stdev=58.39
     lat (usec): min=3, max=5047, avg= 8.55, stdev=58.40
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    7], 40.00th=[    7], 50.00th=[    7], 60.00th=[    8],
     | 70.00th=[    8], 80.00th=[    9], 90.00th=[   10], 95.00th=[   11],
     | 99.00th=[   16], 99.50th=[   49], 99.90th=[   80], 99.95th=[  545],
     | 99.99th=[ 3458]
   bw (  KiB/s): min= 1888, max=18624, per=100.00%, avg=4926.44, stdev=181.58, samples=2872
   iops        : min=  236, max= 2328, avg=615.81, stdev=22.70, samples=2872
  lat (usec)   : 4=0.03%, 10=18.78%, 20=1.07%, 50=0.06%, 100=0.08%
  lat (usec)   : 250=0.01%, 500=0.01%, 750=0.60%, 1000=0.10%
  lat (msec)   : 2=1.46%, 4=62.12%, 10=15.70%, 20=0.01%
  cpu          : usr=0.08%, sys=0.37%, ctx=442249, majf=0, minf=141
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=441995,110727,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=19.2MiB/s (20.1MB/s), 19.2MiB/s-19.2MiB/s (20.1MB/s-20.1MB/s), io=3453MiB (3621MB), run=180005-180005msec
  WRITE: bw=4921KiB/s (5039kB/s), 4921KiB/s-4921KiB/s (5039kB/s-5039kB/s), io=865MiB (907MB), run=180005-180005msec

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 2 (f=2): [_(3),M(1),_(1),M(1),_(2)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Fri Jun 27 09:31:23 2025
  read: IOPS=13.7k, BW=107MiB/s (112MB/s)(19.3GiB/184811msec)
    clat (nsec): min=1015, max=76337k, avg=437240.53, stdev=3232373.71
     lat (nsec): min=1045, max=76337k, avg=437271.03, stdev=3232373.51
    clat percentiles (nsec):
     |  1.00th=[    1320],  5.00th=[    1464], 10.00th=[    1528],
     | 20.00th=[    1592], 30.00th=[    1656], 40.00th=[    1704],
     | 50.00th=[    1768], 60.00th=[    1832], 70.00th=[    1912],
     | 80.00th=[    2008], 90.00th=[    2128], 95.00th=[    2320],
     | 99.00th=[17956864], 99.50th=[29753344], 99.90th=[38535168],
     | 99.95th=[42205184], 99.99th=[46399488]
   bw (  KiB/s): min=36560, max=2074144, per=100.00%, avg=143403.22, stdev=17710.38, samples=2237
   iops        : min= 4570, max=259270, avg=17925.41, stdev=2213.81, samples=2237
  write: IOPS=3432, BW=26.8MiB/s (28.1MB/s)(4957MiB/184811msec); 0 zone resets
    clat (nsec): min=1778, max=35597k, avg=4768.18, stdev=122768.14
     lat (nsec): min=1829, max=35597k, avg=4828.25, stdev=122768.33
    clat percentiles (nsec):
     |  1.00th=[ 3120],  5.00th=[ 3280], 10.00th=[ 3376], 20.00th=[ 3472],
     | 30.00th=[ 3568], 40.00th=[ 3664], 50.00th=[ 3760], 60.00th=[ 3856],
     | 70.00th=[ 4048], 80.00th=[ 4448], 90.00th=[ 5536], 95.00th=[ 6176],
     | 99.00th=[ 9408], 99.50th=[22656], 99.90th=[45312], 99.95th=[51456],
     | 99.99th=[70144]
   bw (  KiB/s): min= 9456, max=522080, per=100.00%, avg=35945.46, stdev=4475.57, samples=2236
   iops        : min= 1182, max=65260, avg=4493.18, stdev=559.45, samples=2236
  lat (usec)   : 2=63.54%, 4=27.73%, 10=6.17%, 20=0.09%, 50=0.11%
  lat (usec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.27%, 4=0.22%, 10=0.64%, 20=0.44%, 50=0.75%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.14%, sys=0.84%, ctx=86694, majf=1, minf=182
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2531997,634432,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=107MiB/s (112MB/s), 107MiB/s-107MiB/s (112MB/s-112MB/s), io=19.3GiB (20.7GB), run=184811-184811msec
  WRITE: bw=26.8MiB/s (28.1MB/s), 26.8MiB/s-26.8MiB/s (28.1MB/s-28.1MB/s), io=4957MiB (5197MB), run=184811-184811msec

Storage Class: dremio-opensearch - gp3 - default IOPS - 128 GB
==============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=20.2MiB/s,w=5232KiB/s][r=2582,w=654 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Fri Jun 27 09:46:49 2025
  read: IOPS=2451, BW=19.2MiB/s (20.1MB/s)(3447MiB/180005msec)
    clat (usec): min=445, max=21235, avg=3260.16, stdev=812.49
     lat (usec): min=445, max=21236, avg=3260.23, stdev=812.49
    clat percentiles (usec):
     |  1.00th=[ 1614],  5.00th=[ 2245], 10.00th=[ 2442], 20.00th=[ 2638],
     | 30.00th=[ 2704], 40.00th=[ 2933], 50.00th=[ 3163], 60.00th=[ 3326],
     | 70.00th=[ 3621], 80.00th=[ 3949], 90.00th=[ 4293], 95.00th=[ 4686],
     | 99.00th=[ 5604], 99.50th=[ 5932], 99.90th=[ 6652], 99.95th=[ 6915],
     | 99.99th=[ 7570]
   bw (  KiB/s): min=13888, max=71968, per=100.00%, avg=19621.88, stdev=538.38, samples=2872
   iops        : min= 1736, max= 8996, avg=2452.74, stdev=67.30, samples=2872
  write: IOPS=614, BW=4914KiB/s (5031kB/s)(864MiB/180005msec); 0 zone resets
    clat (usec): min=3, max=4497, avg= 8.39, stdev=44.76
     lat (usec): min=3, max=4497, avg= 8.50, stdev=44.76
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    6], 10.00th=[    6], 20.00th=[    6],
     | 30.00th=[    7], 40.00th=[    7], 50.00th=[    8], 60.00th=[    8],
     | 70.00th=[    8], 80.00th=[    9], 90.00th=[   10], 95.00th=[   12],
     | 99.00th=[   18], 99.50th=[   47], 99.90th=[   76], 99.95th=[  100],
     | 99.99th=[ 2769]
   bw (  KiB/s): min= 2224, max=18864, per=100.00%, avg=4916.32, stdev=176.55, samples=2872
   iops        : min=  278, max= 2358, avg=614.54, stdev=22.07, samples=2872
  lat (usec)   : 4=0.01%, 10=18.30%, 20=1.57%, 50=0.07%, 100=0.08%
  lat (usec)   : 250=0.01%, 500=0.11%, 750=0.53%, 1000=0.04%
  lat (msec)   : 2=1.39%, 4=63.70%, 10=14.19%, 20=0.01%, 50=0.01%
  cpu          : usr=0.08%, sys=0.37%, ctx=441489, majf=0, minf=127
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=441251,110557,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=19.2MiB/s (20.1MB/s), 19.2MiB/s-19.2MiB/s (20.1MB/s-20.1MB/s), io=3447MiB (3615MB), run=180005-180005msec
  WRITE: bw=4914KiB/s (5031kB/s), 4914KiB/s-4914KiB/s (5031kB/s-5031kB/s), io=864MiB (906MB), run=180005-180005msec
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=114MiB/s,w=28.5MiB/s][r=14.6k,w=3646 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Fri Jun 27 09:50:29 2025
  read: IOPS=14.9k, BW=116MiB/s (122MB/s)(20.5GiB/180027msec)
    clat (nsec): min=1126, max=75330k, avg=534623.25, stdev=3637278.99
     lat (nsec): min=1170, max=75330k, avg=534654.17, stdev=3637278.75
    clat percentiles (nsec):
     |  1.00th=[    1480],  5.00th=[    1576], 10.00th=[    1640],
     | 20.00th=[    1704], 30.00th=[    1768], 40.00th=[    1816],
     | 50.00th=[    1864], 60.00th=[    1928], 70.00th=[    2008],
     | 80.00th=[    2096], 90.00th=[    2224], 95.00th=[    2416],
     | 99.00th=[25559040], 99.50th=[30539776], 99.90th=[39059456],
     | 99.95th=[42205184], 99.99th=[47972352]
   bw (  KiB/s): min=98304, max=349744, per=100.00%, avg=119313.25, stdev=1702.61, samples=2872
   iops        : min=12288, max=43718, avg=14914.16, stdev=212.83, samples=2872
  write: IOPS=3739, BW=29.2MiB/s (30.6MB/s)(5259MiB/180027msec); 0 zone resets
    clat (nsec): min=1824, max=37883k, avg=4885.55, stdev=129622.20
     lat (nsec): min=1876, max=37883k, avg=4944.20, stdev=129622.45
    clat percentiles (nsec):
     |  1.00th=[ 3216],  5.00th=[ 3408], 10.00th=[ 3504], 20.00th=[ 3600],
     | 30.00th=[ 3696], 40.00th=[ 3760], 50.00th=[ 3824], 60.00th=[ 3920],
     | 70.00th=[ 4048], 80.00th=[ 4320], 90.00th=[ 5728], 95.00th=[ 6304],
     | 99.00th=[ 9408], 99.50th=[26496], 99.90th=[49408], 99.95th=[55040],
     | 99.99th=[70144]
   bw (  KiB/s): min=21968, max=89696, per=100.00%, avg=29927.44, stdev=517.77, samples=2872
   iops        : min= 2746, max=11212, avg=3740.93, stdev=64.72, samples=2872
  lat (usec)   : 2=55.67%, 4=35.07%, 10=6.55%, 20=0.08%, 50=0.11%
  lat (usec)   : 100=0.02%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.11%, 4=0.16%, 10=0.79%, 20=0.38%, 50=1.04%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.17%, sys=0.77%, ctx=84029, majf=0, minf=178
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=2683627,673122,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=116MiB/s (122MB/s), 116MiB/s-116MiB/s (122MB/s-122MB/s), io=20.5GiB (22.0GB), run=180027-180027msec
  WRITE: bw=29.2MiB/s (30.6MB/s), 29.2MiB/s-29.2MiB/s (30.6MB/s-30.6MB/s), io=5259MiB (5514MB), run=180027-180027msec

Storage Class: none - emptyDir on r6gd.4xlarge (Graviton)
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=559MiB/s,w=141MiB/s][r=71.5k,w=18.0k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=84: Thu Jul 17 21:25:21 2025
  read: IOPS=64.9k, BW=507MiB/s (532MB/s)(89.1GiB/180001msec)
    clat (usec): min=37, max=2907, avg=120.24, stdev=53.96
     lat (usec): min=37, max=2907, avg=120.31, stdev=53.96
    clat percentiles (usec):
     |  1.00th=[   88],  5.00th=[   91], 10.00th=[   94], 20.00th=[   97],
     | 30.00th=[  102], 40.00th=[  105], 50.00th=[  109], 60.00th=[  112],
     | 70.00th=[  116], 80.00th=[  127], 90.00th=[  151], 95.00th=[  178],
     | 99.00th=[  371], 99.50th=[  469], 99.90th=[  717], 99.95th=[  865],
     | 99.99th=[ 1254]
   bw (  KiB/s): min=68560, max=577088, per=100.00%, avg=522547.15, stdev=13239.59, samples=2854
   iops        : min= 8570, max=72136, avg=65318.39, stdev=1654.95, samples=2854
  write: IOPS=16.2k, BW=127MiB/s (133MB/s)(22.3GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=1095, avg= 4.34, stdev= 4.80
     lat (usec): min=2, max=1095, avg= 4.45, stdev= 4.80
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    4], 10.00th=[    4], 20.00th=[    4],
     | 30.00th=[    4], 40.00th=[    4], 50.00th=[    4], 60.00th=[    5],
     | 70.00th=[    5], 80.00th=[    5], 90.00th=[    6], 95.00th=[    7],
     | 99.00th=[   10], 99.50th=[   11], 99.90th=[   37], 99.95th=[   58],
     | 99.99th=[  241]
   bw (  KiB/s): min=16768, max=157664, per=100.00%, avg=130797.57, stdev=3360.60, samples=2854
   iops        : min= 2096, max=19708, avg=16349.70, stdev=420.07, samples=2854
  lat (usec)   : 4=11.80%, 10=8.09%, 20=0.10%, 50=0.02%, 100=20.98%
  lat (usec)   : 250=57.28%, 500=1.43%, 750=0.23%, 1000=0.05%
  lat (msec)   : 2=0.02%, 4=0.01%
  cpu          : usr=1.05%, sys=7.54%, ctx=11797112, majf=0, minf=75
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=11681018,2923945,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=507MiB/s (532MB/s), 507MiB/s-507MiB/s (532MB/s-532MB/s), io=89.1GiB (95.7GB), run=180001-180001msec
  WRITE: bw=127MiB/s (133MB/s), 127MiB/s-127MiB/s (133MB/s-133MB/s), io=22.3GiB (24.0GB), run=180001-180001msec

Disk stats (read/write):
  nvme2n1: ios=11673616/2437124, sectors=186777872/42417828, merge=0/4, ticks=1318340/697985, in_queue=2016326, util=100.00%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Starting 8 processes
Jobs: 1 (f=1): [_(5),M(1),_(2)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=110: Thu Jul 17 21:31:11 2025
  read: IOPS=143k, BW=1114MiB/s (1168MB/s)(199GiB/182533msec)
    clat (nsec): min=795, max=13397k, avg=46176.46, stdev=315774.21
     lat (nsec): min=845, max=13397k, avg=46224.70, stdev=315774.06
    clat percentiles (nsec):
     |  1.00th=[    844],  5.00th=[    852], 10.00th=[    860],
     | 20.00th=[    876], 30.00th=[    884], 40.00th=[    908],
     | 50.00th=[    972], 60.00th=[   1020], 70.00th=[   1096],
     | 80.00th=[   1224], 90.00th=[   1464], 95.00th=[   1720],
     | 99.00th=[2007040], 99.50th=[2736128], 99.90th=[3457024],
     | 99.95th=[3489792], 99.99th=[3784704]
   bw (  MiB/s): min=   67, max=20006, per=100.00%, avg=1305.89, stdev=162.02, samples=2483
   iops        : min= 8648, max=2560828, avg=167154.03, stdev=20738.89, samples=2483
  write: IOPS=35.6k, BW=278MiB/s (292MB/s)(49.6GiB/182533msec); 0 zone resets
    clat (nsec): min=1305, max=755807, avg=2763.73, stdev=1887.32
     lat (nsec): min=1395, max=755889, avg=2851.77, stdev=1891.05
    clat percentiles (nsec):
     |  1.00th=[ 1800],  5.00th=[ 1880], 10.00th=[ 1928], 20.00th=[ 2040],
     | 30.00th=[ 2128], 40.00th=[ 2288], 50.00th=[ 2512], 60.00th=[ 2768],
     | 70.00th=[ 2896], 80.00th=[ 3088], 90.00th=[ 3600], 95.00th=[ 4192],
     | 99.00th=[ 8256], 99.50th=[ 9152], 99.90th=[28544], 99.95th=[38656],
     | 99.99th=[58624]
   bw (  KiB/s): min=17552, max=5104288, per=100.00%, avg=334303.87, stdev=41380.63, samples=2483
   iops        : min= 2194, max=638036, avg=41787.98, stdev=5172.58, samples=2483
  lat (nsec)   : 1000=44.06%
  lat (usec)   : 2=36.60%, 4=15.74%, 10=1.23%, 20=0.07%, 50=0.04%
  lat (usec)   : 100=0.04%, 250=0.16%, 500=0.21%, 750=0.20%, 1000=0.18%
  lat (msec)   : 2=0.67%, 4=0.80%, 10=0.01%, 20=0.01%
  cpu          : usr=1.04%, sys=5.29%, ctx=943688, majf=0, minf=85
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=26027420,6506767,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1114MiB/s (1168MB/s), 1114MiB/s-1114MiB/s (1168MB/s-1168MB/s), io=199GiB (213GB), run=182533-182533msec
  WRITE: bw=278MiB/s (292MB/s), 278MiB/s-278MiB/s (292MB/s-292MB/s), io=49.6GiB (53.3GB), run=182533-182533msec

Disk stats (read/write):
  nvme2n1: ios=1495978/466681, sectors=382931857/88316219, merge=0/6, ticks=4677740/1075965, in_queue=5753706, util=98.92%

Storage Class: none - emptyDir on m6gd.4xlarge (Graviton)
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=563MiB/s,w=141MiB/s][r=72.1k,w=18.1k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=99: Thu Jul 17 21:39:52 2025
  read: IOPS=64.8k, BW=507MiB/s (531MB/s)(89.0GiB/180001msec)
    clat (usec): min=42, max=6933, avg=120.44, stdev=62.89
     lat (usec): min=42, max=6933, avg=120.51, stdev=62.89
    clat percentiles (usec):
     |  1.00th=[   87],  5.00th=[   91], 10.00th=[   93], 20.00th=[   96],
     | 30.00th=[   99], 40.00th=[  103], 50.00th=[  108], 60.00th=[  112],
     | 70.00th=[  117], 80.00th=[  126], 90.00th=[  153], 95.00th=[  186],
     | 99.00th=[  379], 99.50th=[  537], 99.90th=[  906], 99.95th=[ 1090],
     | 99.99th=[ 1401]
   bw (  KiB/s): min=76320, max=597504, per=100.00%, avg=521580.36, stdev=13862.81, samples=2856
   iops        : min= 9540, max=74688, avg=65197.34, stdev=1732.86, samples=2856
  write: IOPS=16.2k, BW=127MiB/s (133MB/s)(22.3GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=1574, avg= 4.35, stdev= 4.09
     lat (usec): min=2, max=1574, avg= 4.46, stdev= 4.09
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    4], 10.00th=[    4], 20.00th=[    4],
     | 30.00th=[    4], 40.00th=[    4], 50.00th=[    4], 60.00th=[    5],
     | 70.00th=[    5], 80.00th=[    5], 90.00th=[    6], 95.00th=[    6],
     | 99.00th=[   10], 99.50th=[   11], 99.90th=[   40], 99.95th=[   62],
     | 99.99th=[  176]
   bw (  KiB/s): min=18768, max=158048, per=100.00%, avg=130548.38, stdev=3509.30, samples=2856
   iops        : min= 2346, max=19756, avg=16318.24, stdev=438.66, samples=2856
  lat (usec)   : 4=11.22%, 10=8.67%, 20=0.10%, 50=0.01%, 100=26.16%
  lat (usec)   : 250=52.11%, 500=1.26%, 750=0.31%, 1000=0.10%
  lat (msec)   : 2=0.06%, 4=0.01%, 10=0.01%
  cpu          : usr=1.00%, sys=7.59%, ctx=11713460, majf=0, minf=78
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=11669839,2921101,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=507MiB/s (531MB/s), 507MiB/s-507MiB/s (531MB/s-531MB/s), io=89.0GiB (95.6GB), run=180001-180001msec
  WRITE: bw=127MiB/s (133MB/s), 127MiB/s-127MiB/s (133MB/s-133MB/s), io=22.3GiB (23.9GB), run=180001-180001msec

Disk stats (read/write):
  nvme2n1: ios=11653899/2456186, sectors=186462384/42982531, merge=0/4, ticks=1318259/249319, in_queue=1567578, util=99.97%
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=1446MiB/s,w=359MiB/s][r=185k,w=45.9k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=225: Thu Jul 17 21:45:21 2025
  read: IOPS=214k, BW=1676MiB/s (1757MB/s)(295GiB/180003msec)
    clat (nsec): min=804, max=665756k, avg=22694.42, stdev=242101.00
     lat (nsec): min=853, max=665756k, avg=22742.22, stdev=242100.95
    clat percentiles (nsec):
     |  1.00th=[    844],  5.00th=[    852], 10.00th=[    860],
     | 20.00th=[    876], 30.00th=[    884], 40.00th=[    908],
     | 50.00th=[    956], 60.00th=[   1032], 70.00th=[   1096],
     | 80.00th=[   1224], 90.00th=[   1432], 95.00th=[   1688],
     | 99.00th=[ 921600], 99.50th=[1236992], 99.90th=[1646592],
     | 99.95th=[1810432], 99.99th=[3325952]
   bw (  MiB/s): min=  375, max=22037, per=100.00%, avg=2583.23, stdev=255.67, samples=1865
   iops        : min=48004, max=2820848, avg=330653.45, stdev=32726.02, samples=1865
  write: IOPS=53.6k, BW=419MiB/s (439MB/s)(73.6GiB/180003msec); 0 zone resets
    clat (nsec): min=1313, max=2064.3k, avg=2791.57, stdev=1762.20
     lat (nsec): min=1411, max=2064.4k, avg=2879.05, stdev=1765.43
    clat percentiles (nsec):
     |  1.00th=[ 1816],  5.00th=[ 1880], 10.00th=[ 1944], 20.00th=[ 2064],
     | 30.00th=[ 2224], 40.00th=[ 2416], 50.00th=[ 2704], 60.00th=[ 2800],
     | 70.00th=[ 2928], 80.00th=[ 3088], 90.00th=[ 3568], 95.00th=[ 4128],
     | 99.00th=[ 7968], 99.50th=[ 8896], 99.90th=[24192], 99.95th=[33536],
     | 99.99th=[52992]
   bw (  KiB/s): min=94720, max=5629136, per=100.00%, avg=661244.78, stdev=65342.29, samples=1865
   iops        : min=11840, max=703642, avg=82655.60, stdev=8167.79, samples=1865
  lat (nsec)   : 1000=43.80%
  lat (usec)   : 2=36.49%, 4=16.24%, 10=1.19%, 20=0.06%, 50=0.06%
  lat (usec)   : 100=0.06%, 250=0.23%, 500=0.41%, 750=0.40%, 1000=0.38%
  lat (msec)   : 2=0.65%, 4=0.03%, 10=0.01%, 20=0.01%, 750=0.01%
  cpu          : usr=1.54%, sys=6.57%, ctx=1516139, majf=0, minf=91
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=38605225,9650053,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1676MiB/s (1757MB/s), 1676MiB/s-1676MiB/s (1757MB/s-1757MB/s), io=295GiB (316GB), run=180003-180003msec
  WRITE: bw=419MiB/s (439MB/s), 419MiB/s-419MiB/s (439MB/s-439MB/s), io=73.6GiB (79.1GB), run=180003-180003msec

Disk stats (read/write):
  nvme2n1: ios=2147516/564746, sectors=549698289/141837594, merge=0/3, ticks=3369157/3271365, in_queue=6640522, util=99.97%

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