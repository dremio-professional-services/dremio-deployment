Storage Class: dremio-coordinator and dremio-mongodb and dremio-opensearch - managed premium v1 lrs - 5000 IOPS - 1024 GB
=================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(6),m(1),_(1)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=100: Mon Jul 21 14:14:22 2025
  read: IOPS=18.1k, BW=142MiB/s (149MB/s)(28.0GiB/202360msec)
    clat (usec): min=3, max=920114, avg=173.33, stdev=1693.27
     lat (usec): min=3, max=920115, avg=173.36, stdev=1693.27
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    5], 10.00th=[    5], 20.00th=[  122],
     | 30.00th=[  124], 40.00th=[  126], 50.00th=[  130], 60.00th=[  133],
     | 70.00th=[  137], 80.00th=[  141], 90.00th=[  149], 95.00th=[  165],
     | 99.00th=[  326], 99.50th=[  570], 99.90th=[21627], 99.95th=[34866],
     | 99.99th=[55313]
   bw (  KiB/s): min=51474, max=606202, per=100.00%, avg=411861.35, stdev=20035.81, samples=1287
   iops        : min= 6434, max=75775, avg=51481.68, stdev=2504.49, samples=1287
  write: IOPS=4550, BW=35.5MiB/s (37.3MB/s)(7194MiB/202360msec); 0 zone resets
    clat (usec): min=4, max=188587, avg= 7.74, stdev=421.68
     lat (usec): min=4, max=188587, avg= 7.78, stdev=421.68
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    5], 20.00th=[    6],
     | 30.00th=[    6], 40.00th=[    6], 50.00th=[    6], 60.00th=[    6],
     | 70.00th=[    7], 80.00th=[    7], 90.00th=[    8], 95.00th=[    9],
     | 99.00th=[   12], 99.50th=[   15], 99.90th=[   40], 99.95th=[   63],
     | 99.99th=[  285]
   bw (  KiB/s): min=12364, max=157678, per=100.00%, avg=104016.58, stdev=4944.67, samples=1272
   iops        : min= 1545, max=19708, avg=13001.00, stdev=618.11, samples=1272
  lat (usec)   : 4=1.14%, 10=31.57%, 20=0.39%, 50=0.30%, 100=0.08%
  lat (usec)   : 250=65.22%, 500=0.85%, 750=0.14%, 1000=0.04%
  lat (msec)   : 2=0.06%, 4=0.04%, 10=0.06%, 20=0.04%, 50=0.08%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%, 1000=0.01%
  cpu          : usr=0.20%, sys=3.94%, ctx=3136638, majf=0, minf=160
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=3672571,920774,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=142MiB/s (149MB/s), 142MiB/s-142MiB/s (149MB/s-149MB/s), io=28.0GiB (30.1GB), run=202360-202360msec
  WRITE: bw=35.5MiB/s (37.3MB/s), 35.5MiB/s-35.5MiB/s (37.3MB/s-37.3MB/s), io=7194MiB (7543MB), run=202360-202360msec

Disk stats (read/write):
  nvme0n2: ios=3070129/879045, merge=0/980, ticks=588981/227751973, in_queue=228340956, util=100.00%
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(5),M(1),_(2)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=141: Mon Jul 21 14:47:33 2025
  read: IOPS=91.8k, BW=717MiB/s (752MB/s)(129GiB/184078msec)
    clat (nsec): min=801, max=2242.9M, avg=72016.29, stdev=4344334.48
     lat (nsec): min=821, max=2242.9M, avg=72046.54, stdev=4344334.54
    clat percentiles (nsec):
     |  1.00th=[     868],  5.00th=[    1080], 10.00th=[    1128],
     | 20.00th=[    1176], 30.00th=[    1224], 40.00th=[    1272],
     | 50.00th=[    1320], 60.00th=[    1368], 70.00th=[    1448],
     | 80.00th=[    1528], 90.00th=[    1688], 95.00th=[    1880],
     | 99.00th=[    5344], 99.50th=[  354304], 99.90th=[ 4751360],
     | 99.95th=[41680896], 99.99th=[64225280]
   bw (  KiB/s): min= 5280, max=12490208, per=100.00%, avg=937697.64, stdev=121640.26, samples=2314
   iops        : min=  660, max=1561276, avg=117212.20, stdev=15205.04, samples=2314
  write: IOPS=23.0k, BW=179MiB/s (188MB/s)(32.3GiB/184078msec); 0 zone resets
    clat (usec): min=2, max=1113.9k, avg= 4.57, stdev=725.80
     lat (usec): min=2, max=1113.9k, avg= 4.61, stdev=725.80
    clat percentiles (nsec):
     |  1.00th=[ 2832],  5.00th=[ 2960], 10.00th=[ 3024], 20.00th=[ 3088],
     | 30.00th=[ 3184], 40.00th=[ 3280], 50.00th=[ 3472], 60.00th=[ 3728],
     | 70.00th=[ 4128], 80.00th=[ 4576], 90.00th=[ 5216], 95.00th=[ 6240],
     | 99.00th=[10048], 99.50th=[12992], 99.90th=[23168], 99.95th=[36096],
     | 99.99th=[73216]
   bw (  KiB/s): min= 1648, max=3124576, per=100.00%, avg=235058.21, stdev=30447.61, samples=2310
   iops        : min=  206, max=390574, avg=29382.22, stdev=3805.96, samples=2310
  lat (nsec)   : 1000=2.99%
  lat (usec)   : 2=74.28%, 4=15.41%, 10=6.43%, 20=0.21%, 50=0.04%
  lat (usec)   : 100=0.01%, 250=0.07%, 500=0.26%, 750=0.10%, 1000=0.06%
  lat (msec)   : 2=0.05%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.06%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2000=0.01%, >=2000=0.01%
  cpu          : usr=0.56%, sys=6.97%, ctx=106194, majf=0, minf=180
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=16898851,4228802,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=717MiB/s (752MB/s), 717MiB/s-717MiB/s (752MB/s-752MB/s), io=129GiB (138GB), run=184078-184078msec
  WRITE: bw=179MiB/s (188MB/s), 179MiB/s-179MiB/s (188MB/s-188MB/s), io=32.3GiB (34.6GB), run=184078-184078msec

Disk stats (read/write):
  nvme0n2: ios=692998/126680, merge=0/29090, ticks=10288047/89841677, in_queue=100129727, util=99.66%

Storage Class: dremio-coordinator and dremio-mongodb and dremio-opensearch - managed premium v1 zrs - 5000 IOPS - 1024 GB
=================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(7),m(1)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Mon Jul 21 15:15:30 2025
  read: IOPS=29.6k, BW=232MiB/s (243MB/s)(46.8GiB/207032msec)
    clat (usec): min=38, max=150093, avg=231.57, stdev=1627.09
     lat (usec): min=38, max=150093, avg=231.60, stdev=1627.09
    clat percentiles (usec):
     |  1.00th=[   45],  5.00th=[   66], 10.00th=[  123], 20.00th=[  125],
     | 30.00th=[  127], 40.00th=[  130], 50.00th=[  133], 60.00th=[  137],
     | 70.00th=[  139], 80.00th=[  143], 90.00th=[  151], 95.00th=[  165],
     | 99.00th=[  371], 99.50th=[ 1205], 99.90th=[26870], 99.95th=[37487],
     | 99.99th=[45351]
   bw (  KiB/s): min=45840, max=737872, per=100.00%, avg=273544.32, stdev=15844.55, samples=2868
   iops        : min= 5730, max=92234, avg=34193.05, stdev=1980.57, samples=2868
  write: IOPS=7424, BW=58.0MiB/s (60.8MB/s)(11.7GiB/207032msec); 0 zone resets
    clat (usec): min=4, max=133783, avg= 8.64, stdev=435.10
     lat (usec): min=4, max=133783, avg= 8.68, stdev=435.10
    clat percentiles (nsec):
     |  1.00th=[ 4576],  5.00th=[ 4704], 10.00th=[ 4832], 20.00th=[ 4960],
     | 30.00th=[ 5088], 40.00th=[ 5216], 50.00th=[ 5344], 60.00th=[ 5600],
     | 70.00th=[ 6368], 80.00th=[ 6688], 90.00th=[ 7392], 95.00th=[ 8384],
     | 99.00th=[11456], 99.50th=[14272], 99.90th=[39168], 99.95th=[59648],
     | 99.99th=[91648]
   bw (  KiB/s): min=11072, max=188832, per=100.00%, avg=68528.86, stdev=3980.29, samples=2868
   iops        : min= 1384, max=23604, avg=8566.11, stdev=497.54, samples=2868
  lat (usec)   : 10=19.67%, 20=0.32%, 50=3.25%, 100=0.84%, 250=74.52%
  lat (usec)   : 500=0.83%, 750=0.14%, 1000=0.03%
  lat (msec)   : 2=0.04%, 4=0.03%, 10=0.05%, 20=0.06%, 50=0.22%
  lat (msec)   : 100=0.01%, 250=0.01%
  cpu          : usr=0.41%, sys=4.98%, ctx=6144892, majf=0, minf=157
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=6135594,1537087,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=232MiB/s (243MB/s), 232MiB/s-232MiB/s (243MB/s-243MB/s), io=46.8GiB (50.3GB), run=207032-207032msec
  WRITE: bw=58.0MiB/s (60.8MB/s), 58.0MiB/s-58.0MiB/s (60.8MB/s-60.8MB/s), io=11.7GiB (12.6GB), run=207032-207032msec

Disk stats (read/write):
  nvme0n2: ios=6135593/881049, merge=0/147, ticks=1339840/51056275, in_queue=52396120, util=100.00%
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Starting 8 processes
Jobs: 1 (f=1): [_(3),M(1),_(4)][100.0%][r=182MiB/s,w=45.0MiB/s][r=23.2k,w=5757 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Mon Jul 21 15:22:40 2025
  read: IOPS=92.5k, BW=722MiB/s (757MB/s)(128GiB/181069msec)
    clat (nsec): min=811, max=2447.7M, avg=73734.23, stdev=3857102.60
     lat (nsec): min=841, max=2447.7M, avg=73764.08, stdev=3857102.63
    clat percentiles (nsec):
     |  1.00th=[    1096],  5.00th=[    1128], 10.00th=[    1160],
     | 20.00th=[    1208], 30.00th=[    1240], 40.00th=[    1288],
     | 50.00th=[    1336], 60.00th=[    1384], 70.00th=[    1448],
     | 80.00th=[    1528], 90.00th=[    1688], 95.00th=[    1880],
     | 99.00th=[    4384], 99.50th=[  391168], 99.90th=[37486592],
     | 99.95th=[42729472], 99.99th=[62128128]
   bw (  KiB/s): min= 6672, max=10688384, per=100.00%, avg=892004.75, stdev=103822.67, samples=2408
   iops        : min=  834, max=1336048, avg=111500.59, stdev=12977.83, samples=2408
  write: IOPS=23.1k, BW=181MiB/s (190MB/s)(32.0GiB/181069msec); 0 zone resets
    clat (usec): min=2, max=1589.9k, avg= 5.30, stdev=1158.98
     lat (usec): min=2, max=1589.9k, avg= 5.35, stdev=1158.98
    clat percentiles (nsec):
     |  1.00th=[ 2832],  5.00th=[ 2960], 10.00th=[ 3024], 20.00th=[ 3088],
     | 30.00th=[ 3184], 40.00th=[ 3280], 50.00th=[ 3440], 60.00th=[ 3696],
     | 70.00th=[ 4080], 80.00th=[ 4512], 90.00th=[ 5216], 95.00th=[ 6112],
     | 99.00th=[ 9792], 99.50th=[12608], 99.90th=[23680], 99.95th=[40192],
     | 99.99th=[81408]
   bw (  KiB/s): min= 2160, max=2673984, per=100.00%, avg=223536.10, stdev=26004.48, samples=2405
   iops        : min=  270, max=334248, avg=27941.95, stdev=3250.56, samples=2405
  lat (nsec)   : 1000=0.05%
  lat (usec)   : 2=77.31%, 4=15.57%, 10=6.25%, 20=0.18%, 50=0.03%
  lat (usec)   : 100=0.01%, 250=0.06%, 500=0.20%, 750=0.10%, 1000=0.07%
  lat (msec)   : 2=0.07%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.07%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2000=0.01%, >=2000=0.01%
  cpu          : usr=0.53%, sys=7.28%, ctx=100651, majf=0, minf=192
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=16740401,4189499,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=722MiB/s (757MB/s), 722MiB/s-722MiB/s (757MB/s-757MB/s), io=128GiB (137GB), run=181069-181069msec
  WRITE: bw=181MiB/s (190MB/s), 181MiB/s-181MiB/s (190MB/s-190MB/s), io=32.0GiB (34.3GB), run=181069-181069msec

Disk stats (read/write):
  nvme0n2: ios=500818/125375, merge=0/197, ticks=8660596/76094703, in_queue=84755303, util=99.49%

Storage Class: dremio-coordinator and dremio-mongodband dremio-opensearch - managed premium v2 lrs - 5000 IOPS - 1024 GB
=================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=39.9MiB/s,w=9.82MiB/s][r=5108,w=1257 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=41: Mon Jul 21 15:38:12 2025
  read: IOPS=4219, BW=33.0MiB/s (34.6MB/s)(5934MiB/180002msec)
    clat (usec): min=123, max=101125, avg=1893.01, stdev=4039.59
     lat (usec): min=123, max=101125, avg=1893.05, stdev=4039.61
    clat percentiles (usec):
     |  1.00th=[  519],  5.00th=[ 1012], 10.00th=[ 1020], 20.00th=[ 1029],
     | 30.00th=[ 1336], 40.00th=[ 1549], 50.00th=[ 1565], 60.00th=[ 1565],
     | 70.00th=[ 1582], 80.00th=[ 2040], 90.00th=[ 2057], 95.00th=[ 2073],
     | 99.00th=[ 6718], 99.50th=[32113], 99.90th=[51643], 99.95th=[52167],
     | 99.99th=[87557]
   bw (  KiB/s): min= 1008, max=99760, per=100.00%, avg=33760.27, stdev=2113.96, samples=2872
   iops        : min=  126, max=12470, avg=4220.03, stdev=264.24, samples=2872
  write: IOPS=1055, BW=8446KiB/s (8649kB/s)(1485MiB/180002msec); 0 zone resets
    clat (usec): min=4, max=85330, avg= 8.59, stdev=228.43
     lat (usec): min=4, max=85330, avg= 8.66, stdev=228.43
    clat percentiles (usec):
     |  1.00th=[    5],  5.00th=[    5], 10.00th=[    6], 20.00th=[    6],
     | 30.00th=[    7], 40.00th=[    7], 50.00th=[    8], 60.00th=[    8],
     | 70.00th=[    9], 80.00th=[    9], 90.00th=[   11], 95.00th=[   12],
     | 99.00th=[   17], 99.50th=[   20], 99.90th=[   40], 99.95th=[   77],
     | 99.99th=[ 1057]
   bw (  KiB/s): min=  128, max=26000, per=100.00%, avg=8581.82, stdev=536.08, samples=2827
   iops        : min=   16, max= 3250, avg=1072.73, stdev=67.01, samples=2827
  lat (usec)   : 10=17.77%, 20=2.15%, 50=0.08%, 100=0.01%, 250=0.20%
  lat (usec)   : 500=0.54%, 750=1.61%, 1000=1.23%
  lat (msec)   : 2=57.06%, 4=18.35%, 10=0.23%, 20=0.02%, 50=0.38%
  lat (msec)   : 100=0.37%, 250=0.01%
  cpu          : usr=0.08%, sys=0.74%, ctx=759661, majf=0, minf=133
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=759530,190048,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=33.0MiB/s (34.6MB/s), 33.0MiB/s-33.0MiB/s (34.6MB/s-34.6MB/s), io=5934MiB (6222MB), run=180002-180002msec
  WRITE: bw=8446KiB/s (8649kB/s), 8446KiB/s-8446KiB/s (8649kB/s-8649kB/s), io=1485MiB (1557MB), run=180002-180002msec

Disk stats (read/write):
  nvme0n2: ios=759441/173867, merge=0/70, ticks=1428098/7912343, in_queue=9340442, util=100.00%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Starting 8 processes
Jobs: 8 (f=8): [M(8)][100.0%][r=32.0MiB/s,w=8752KiB/s][r=4096,w=1094 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=67: Mon Jul 21 15:41:50 2025
  read: IOPS=20.5k, BW=160MiB/s (168MB/s)(28.2GiB/180368msec)
    clat (nsec): min=871, max=802693k, avg=388842.30, stdev=6915263.24
     lat (nsec): min=901, max=802693k, avg=388871.08, stdev=6915263.13
    clat percentiles (nsec):
     |  1.00th=[     1012],  5.00th=[     1096], 10.00th=[     1112],
     | 20.00th=[     1128], 30.00th=[     1144], 40.00th=[     1160],
     | 50.00th=[     1192], 60.00th=[     1224], 70.00th=[     1240],
     | 80.00th=[     1272], 90.00th=[     1352], 95.00th=[     1480],
     | 99.00th=[     3248], 99.50th=[ 35913728], 99.90th=[ 61079552],
     | 99.95th=[ 74973184], 99.99th=[362807296]
   bw (  KiB/s): min=16448, max=797120, per=100.00%, avg=165925.54, stdev=9684.33, samples=2847
   iops        : min= 2056, max=99640, avg=20740.69, stdev=1210.54, samples=2847
  write: IOPS=5131, BW=40.1MiB/s (42.0MB/s)(7231MiB/180368msec); 0 zone resets
    clat (usec): min=2, max=401091, avg= 4.09, stdev=432.00
     lat (usec): min=2, max=401091, avg= 4.14, stdev=432.00
    clat percentiles (nsec):
     |  1.00th=[ 2800],  5.00th=[ 2864], 10.00th=[ 2928], 20.00th=[ 2992],
     | 30.00th=[ 3024], 40.00th=[ 3056], 50.00th=[ 3088], 60.00th=[ 3120],
     | 70.00th=[ 3216], 80.00th=[ 3312], 90.00th=[ 3824], 95.00th=[ 5856],
     | 99.00th=[ 9536], 99.50th=[10560], 99.90th=[26752], 99.95th=[45824],
     | 99.99th=[84480]
   bw (  KiB/s): min= 3616, max=202064, per=100.00%, avg=41622.67, stdev=2449.90, samples=2846
   iops        : min=  452, max=25258, avg=5202.83, stdev=306.24, samples=2846
  lat (nsec)   : 1000=0.40%
  lat (usec)   : 2=78.04%, 4=18.95%, 10=1.81%, 20=0.12%, 50=0.04%
  lat (usec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.02%, 20=0.03%, 50=0.39%
  lat (msec)   : 100=0.14%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  cpu          : usr=0.12%, sys=1.14%, ctx=29141, majf=0, minf=161
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=3690795,925515,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=160MiB/s (168MB/s), 160MiB/s-160MiB/s (168MB/s-168MB/s), io=28.2GiB (30.2GB), run=180368-180368msec
  WRITE: bw=40.1MiB/s (42.0MB/s), 40.1MiB/s-40.1MiB/s (42.0MB/s-42.0MB/s), io=7231MiB (7582MB), run=180368-180368msec

Disk stats (read/write):
  nvme0n2: ios=115804/27311, merge=0/70, ticks=11072527/11305110, in_queue=22377639, util=99.87%

Storage Class: dremio-zk and dremio-nats and dremio-logs - managed v1 lrs - default IOPS - 16 GB
=====================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [_(4),m(1),_(3)][100.0%][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=73: Mon Jul 21 15:52:36 2025
  read: IOPS=3729, BW=29.1MiB/s (30.5MB/s)(6529MiB/224112msec)
    clat (usec): min=40, max=2094.5k, avg=1448.78, stdev=22120.74
     lat (usec): min=40, max=2094.5k, avg=1448.82, stdev=22120.75
    clat percentiles (usec):
     |  1.00th=[    45],  5.00th=[    47], 10.00th=[    50], 20.00th=[    59],
     | 30.00th=[    61], 40.00th=[    62], 50.00th=[    62], 60.00th=[    63],
     | 70.00th=[    63], 80.00th=[    64], 90.00th=[    66], 95.00th=[    69],
     | 99.00th=[ 43779], 99.50th=[ 47449], 99.90th=[396362], 99.95th=[455082],
     | 99.99th=[809501]
   bw (  KiB/s): min=  128, max=640640, per=100.00%, avg=48305.46, stdev=18032.00, samples=2313
   iops        : min=   16, max=80080, avg=6038.04, stdev=2254.00, samples=2313
  write: IOPS=932, BW=7462KiB/s (7641kB/s)(1633MiB/224112msec); 0 zone resets
    clat (usec): min=4, max=905316, avg=144.80, stdev=7384.24
     lat (usec): min=4, max=905317, avg=144.88, stdev=7384.24
    clat percentiles (usec):
     |  1.00th=[     5],  5.00th=[     5], 10.00th=[     5], 20.00th=[     5],
     | 30.00th=[     5], 40.00th=[     5], 50.00th=[     6], 60.00th=[     6],
     | 70.00th=[     7], 80.00th=[     7], 90.00th=[     8], 95.00th=[     9],
     | 99.00th=[    18], 99.50th=[    22], 99.90th=[    38], 99.95th=[   102],
     | 99.99th=[304088]
   bw (  KiB/s): min=  128, max=165712, per=100.00%, avg=20121.59, stdev=5692.69, samples=1352
   iops        : min=   16, max=20714, avg=2515.08, stdev=711.59, samples=1352
  lat (usec)   : 10=19.39%, 20=0.49%, 50=7.99%, 100=70.53%, 250=0.43%
  lat (usec)   : 500=0.11%, 750=0.03%, 1000=0.01%
  lat (msec)   : 2=0.02%, 4=0.01%, 10=0.02%, 20=0.11%, 50=0.48%
  lat (msec)   : 100=0.14%, 250=0.09%, 500=0.11%, 750=0.02%, 1000=0.01%
  lat (msec)   : 2000=0.01%, >=2000=0.01%
  cpu          : usr=0.05%, sys=0.71%, ctx=842286, majf=0, minf=178
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=835744,209037,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=29.1MiB/s (30.5MB/s), 29.1MiB/s-29.1MiB/s (30.5MB/s-30.5MB/s), io=6529MiB (6846MB), run=224112-224112msec
  WRITE: bw=7462KiB/s (7641kB/s), 7462KiB/s-7462KiB/s (7641kB/s-7641kB/s), io=1633MiB (1712MB), run=224112-224112msec

Disk stats (read/write):
  nvme0n2: ios=835743/131053, merge=0/79, ticks=1169024/134574706, in_queue=135743734, util=100.00%
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=761MiB/s,w=193MiB/s][r=97.4k,w=24.7k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=101: Mon Jul 21 15:56:28 2025
  read: IOPS=62.3k, BW=487MiB/s (510MB/s)(85.5GiB/180030msec)
    clat (nsec): min=791, max=2551.9M, avg=108770.69, stdev=6872812.51
     lat (nsec): min=811, max=2551.9M, avg=108801.94, stdev=6872812.98
    clat percentiles (nsec):
     |  1.00th=[     1080],  5.00th=[     1128], 10.00th=[     1160],
     | 20.00th=[     1224], 30.00th=[     1272], 40.00th=[     1336],
     | 50.00th=[     1400], 60.00th=[     1448], 70.00th=[     1528],
     | 80.00th=[     1640], 90.00th=[     1848], 95.00th=[     2064],
     | 99.00th=[     3952], 99.50th=[   280576], 99.90th=[   667648],
     | 99.95th=[ 41156608], 99.99th=[299892736]
   bw (  KiB/s): min=  368, max=6471984, per=100.00%, avg=642940.39, stdev=123807.69, samples=2221
   iops        : min=   46, max=808998, avg=80367.46, stdev=15475.96, samples=2221
  write: IOPS=15.6k, BW=122MiB/s (128MB/s)(21.4GiB/180030msec); 0 zone resets
    clat (usec): min=2, max=992087, avg= 7.01, stdev=1238.61
     lat (usec): min=2, max=992087, avg= 7.06, stdev=1238.61
    clat percentiles (nsec):
     |  1.00th=[ 2832],  5.00th=[ 2992], 10.00th=[ 3088], 20.00th=[ 3248],
     | 30.00th=[ 3504], 40.00th=[ 3920], 50.00th=[ 4320], 60.00th=[ 4512],
     | 70.00th=[ 4704], 80.00th=[ 5216], 90.00th=[ 6176], 95.00th=[ 7456],
     | 99.00th=[11712], 99.50th=[14400], 99.90th=[23680], 99.95th=[34048],
     | 99.99th=[88576]
   bw (  KiB/s): min=  400, max=1617296, per=100.00%, avg=162502.13, stdev=31077.84, samples=2199
   iops        : min=   50, max=202164, avg=20312.59, stdev=3884.73, samples=2199
  lat (nsec)   : 1000=0.31%
  lat (usec)   : 2=74.68%, 4=12.52%, 10=11.59%, 20=0.33%, 50=0.04%
  lat (usec)   : 100=0.01%, 250=0.03%, 500=0.34%, 750=0.06%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.04%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2000=0.01%, >=2000=0.01%
  cpu          : usr=0.36%, sys=4.40%, ctx=46322, majf=0, minf=183
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=11211815,2806033,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=487MiB/s (510MB/s), 487MiB/s-487MiB/s (510MB/s-510MB/s), io=85.5GiB (91.8GB), run=180030-180030msec
  WRITE: bw=122MiB/s (128MB/s), 122MiB/s-122MiB/s (128MB/s-128MB/s), io=21.4GiB (23.0GB), run=180030-180030msec

Disk stats (read/write):
  nvme0n2: ios=283814/93300, merge=0/125, ticks=8378195/73322661, in_queue=81700859, util=100.00%

Storage Class: dremio-zk and dremio-nats and dremio-logs - managed v1 zrs - default IOPS - 16 GB
=====================================================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=17.0MiB/s,w=4164KiB/s][r=2170,w=520 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=40: Mon Jul 21 16:03:45 2025
  read: IOPS=2632, BW=20.6MiB/s (21.6MB/s)(3702MiB/180018msec)
    clat (usec): min=41, max=763845, avg=2941.43, stdev=17766.56
     lat (usec): min=41, max=763846, avg=2941.48, stdev=17766.59
    clat percentiles (usec):
     |  1.00th=[    45],  5.00th=[    46], 10.00th=[    47], 20.00th=[    48],
     | 30.00th=[    50], 40.00th=[    55], 50.00th=[    61], 60.00th=[    62],
     | 70.00th=[    63], 80.00th=[    64], 90.00th=[    68], 95.00th=[   245],
     | 99.00th=[ 60556], 99.50th=[ 63701], 99.90th=[341836], 99.95th=[396362],
     | 99.99th=[413139]
   bw (  KiB/s): min=  128, max=955536, per=100.00%, avg=21144.09, stdev=10199.94, samples=2864
   iops        : min=   16, max=119442, avg=2643.01, stdev=1274.99, samples=2864
  write: IOPS=658, BW=5271KiB/s (5397kB/s)(927MiB/180018msec); 0 zone resets
    clat (usec): min=4, max=415442, avg=388.25, stdev=10677.36
     lat (usec): min=4, max=415442, avg=388.32, stdev=10677.36
    clat percentiles (usec):
     |  1.00th=[     5],  5.00th=[     5], 10.00th=[     5], 20.00th=[     5],
     | 30.00th=[     5], 40.00th=[     6], 50.00th=[     6], 60.00th=[     6],
     | 70.00th=[     7], 80.00th=[     8], 90.00th=[    10], 95.00th=[    15],
     | 99.00th=[    25], 99.50th=[    28], 99.90th=[208667], 99.95th=[304088],
     | 99.99th=[404751]
   bw (  KiB/s): min=  128, max=243600, per=100.00%, avg=5852.10, stdev=2694.86, samples=2591
   iops        : min=   16, max=30450, avg=731.51, stdev=336.86, samples=2591
  lat (usec)   : 10=18.22%, 20=1.31%, 50=23.95%, 100=51.63%, 250=0.87%
  lat (usec)   : 500=0.16%, 750=0.05%, 1000=0.02%
  lat (msec)   : 2=0.03%, 4=0.01%, 10=0.01%, 20=0.05%, 50=2.77%
  lat (msec)   : 100=0.65%, 250=0.15%, 500=0.12%, 750=0.01%, 1000=0.01%
  cpu          : usr=0.05%, sys=0.43%, ctx=474100, majf=0, minf=172
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=473836,118608,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=20.6MiB/s (21.6MB/s), 20.6MiB/s-20.6MiB/s (21.6MB/s-21.6MB/s), io=3702MiB (3882MB), run=180018-180018msec
  WRITE: bw=5271KiB/s (5397kB/s), 5271KiB/s-5271KiB/s (5397kB/s-5397kB/s), io=927MiB (972MB), run=180018-180018msec

Disk stats (read/write):
  nvme0n2: ios=473580/108584, merge=0/79, ticks=1372063/46781047, in_queue=48153114, util=100.00%
------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=1G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 1 (f=1): [M(1),_(7)][100.0%][r=16KiB/s][r=2 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=66: Mon Jul 21 16:09:22 2025
  read: IOPS=67.0k, BW=524MiB/s (549MB/s)(93.8GiB/183480msec)
    clat (nsec): min=801, max=3046.0M, avg=94938.91, stdev=6047784.82
     lat (nsec): min=831, max=3046.0M, avg=94969.54, stdev=6047785.25
    clat percentiles (nsec):
     |  1.00th=[     1080],  5.00th=[     1128], 10.00th=[     1160],
     | 20.00th=[     1240], 30.00th=[     1288], 40.00th=[     1336],
     | 50.00th=[     1400], 60.00th=[     1448], 70.00th=[     1528],
     | 80.00th=[     1640], 90.00th=[     1848], 95.00th=[     2064],
     | 99.00th=[     4512], 99.50th=[   268288], 99.90th=[   667648],
     | 99.95th=[ 44302336], 99.99th=[206569472]
   bw (  KiB/s): min=  496, max=6369216, per=100.00%, avg=713774.31, stdev=122195.34, samples=2207
   iops        : min=   62, max=796152, avg=89221.71, stdev=15274.42, samples=2207
  write: IOPS=16.8k, BW=131MiB/s (137MB/s)(23.5GiB/183480msec); 0 zone resets
    clat (usec): min=2, max=1908.6k, avg= 8.42, stdev=2033.10
     lat (usec): min=2, max=1908.6k, avg= 8.47, stdev=2033.10
    clat percentiles (nsec):
     |  1.00th=[ 2864],  5.00th=[ 3024], 10.00th=[ 3088], 20.00th=[ 3280],
     | 30.00th=[ 3472], 40.00th=[ 3984], 50.00th=[ 4384], 60.00th=[ 4576],
     | 70.00th=[ 4768], 80.00th=[ 5344], 90.00th=[ 6240], 95.00th=[ 7584],
     | 99.00th=[11840], 99.50th=[14656], 99.90th=[24192], 99.95th=[36096],
     | 99.99th=[97792]
   bw (  KiB/s): min=  176, max=1588768, per=100.00%, avg=179835.43, stdev=30644.96, samples=2193
   iops        : min=   22, max=198596, avg=22479.31, stdev=3830.62, samples=2193
  lat (nsec)   : 1000=0.33%
  lat (usec)   : 2=74.83%, 4=11.97%, 10=11.96%, 20=0.35%, 50=0.04%
  lat (usec)   : 100=0.01%, 250=0.05%, 500=0.34%, 750=0.04%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.04%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%, 750=0.01%, 1000=0.01%
  lat (msec)   : 2000=0.01%, >=2000=0.01%
  cpu          : usr=0.41%, sys=4.87%, ctx=41064, majf=0, minf=188
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=12295252,3077590,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=524MiB/s (549MB/s), 524MiB/s-524MiB/s (549MB/s-549MB/s), io=93.8GiB (101GB), run=183480-183480msec
  WRITE: bw=131MiB/s (137MB/s), 131MiB/s-131MiB/s (137MB/s-137MB/s), io=23.5GiB (25.2GB), run=183480-183480msec

Disk stats (read/write):
  nvme0n2: ios=310309/96493, merge=0/133, ticks=7776583/84545038, in_queue=92321624, util=99.93%

Storage Class: none - hostPath on Standard_E16ds_v5 (16 CPUs) - Azure Linux
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
kvstore_test: Laying out IO file (1 file / 8192MiB)
Jobs: 8 (f=8): [m(8)][100.0%][r=417MiB/s,w=104MiB/s][r=53.4k,w=13.3k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=83: Tue Jul 22 12:38:46 2025
  read: IOPS=46.0k, BW=360MiB/s (377MB/s)(63.2GiB/180001msec)
    clat (usec): min=90, max=82921, avg=170.67, stdev=784.21
     lat (usec): min=90, max=82921, avg=170.74, stdev=784.21
    clat percentiles (usec):
     |  1.00th=[  110],  5.00th=[  117], 10.00th=[  121], 20.00th=[  127],
     | 30.00th=[  133], 40.00th=[  137], 50.00th=[  141], 60.00th=[  147],
     | 70.00th=[  153], 80.00th=[  161], 90.00th=[  182], 95.00th=[  208],
     | 99.00th=[  449], 99.50th=[  562], 99.90th=[ 1663], 99.95th=[26608],
     | 99.99th=[35914]
   bw (  KiB/s): min=34976, max=450832, per=100.00%, avg=369963.95, stdev=14786.01, samples=2859
   iops        : min= 4372, max=56354, avg=46245.49, stdev=1848.25, samples=2859
  write: IOPS=11.5k, BW=90.1MiB/s (94.4MB/s)(15.8GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=3303, avg= 5.06, stdev= 6.13
     lat (usec): min=2, max=3303, avg= 5.15, stdev= 6.14
    clat percentiles (usec):
     |  1.00th=[    3],  5.00th=[    4], 10.00th=[    4], 20.00th=[    4],
     | 30.00th=[    4], 40.00th=[    5], 50.00th=[    5], 60.00th=[    5],
     | 70.00th=[    6], 80.00th=[    6], 90.00th=[    8], 95.00th=[    9],
     | 99.00th=[   15], 99.50th=[   18], 99.90th=[   50], 99.95th=[   69],
     | 99.99th=[  206]
   bw (  KiB/s): min= 7968, max=119360, per=100.00%, avg=92669.05, stdev=3734.85, samples=2859
   iops        : min=  996, max=14920, avg=11583.63, stdev=466.86, samples=2859
  lat (usec)   : 4=7.94%, 10=11.44%, 20=0.57%, 50=0.05%, 100=0.06%
  lat (usec)   : 250=77.83%, 500=1.51%, 750=0.40%, 1000=0.07%
  lat (msec)   : 2=0.05%, 4=0.02%, 10=0.01%, 20=0.01%, 50=0.04%
  lat (msec)   : 100=0.01%
  cpu          : usr=0.81%, sys=6.91%, ctx=8287186, majf=0, minf=88
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=8283966,2074898,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=360MiB/s (377MB/s), 360MiB/s-360MiB/s (377MB/s-377MB/s), io=63.2GiB (67.9GB), run=180001-180001msec
  WRITE: bw=90.1MiB/s (94.4MB/s), 90.1MiB/s-90.1MiB/s (94.4MB/s-94.4MB/s), io=15.8GiB (17.0GB), run=180001-180001msec

Disk stats (read/write):
  sdb: ios=8276855/1866285, sectors=132429680/32038120, merge=0/97, ticks=1298544/2753907, in_queue=4052451, util=77.65%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
kvstore_test: (groupid=0, jobs=8): err= 0: pid=109: Tue Jul 22 12:45:56 2025
  read: IOPS=172k, BW=1348MiB/s (1413MB/s)(238GiB/180899msec)
    clat (nsec): min=480, max=301175k, avg=44007.54, stdev=1357052.12
     lat (nsec): min=505, max=301175k, avg=44041.35, stdev=1357052.13
    clat percentiles (nsec):
     |  1.00th=[     596],  5.00th=[     620], 10.00th=[     644],
     | 20.00th=[     676], 30.00th=[     716], 40.00th=[     756],
     | 50.00th=[     812], 60.00th=[     884], 70.00th=[     980],
     | 80.00th=[    1112], 90.00th=[    1320], 95.00th=[    1608],
     | 99.00th=[  220160], 99.50th=[  292864], 99.90th=[  880640],
     | 99.95th=[38010880], 99.99th=[53739520]
   bw (  MiB/s): min=    9, max=18571, per=100.00%, avg=1375.65, stdev=167.03, samples=2835
   iops        : min= 1276, max=2377130, avg=176083.58, stdev=21379.48, samples=2835
  write: IOPS=43.1k, BW=337MiB/s (353MB/s)(59.5GiB/180899msec); 0 zone resets
    clat (nsec): min=1284, max=46407k, avg=3440.02, stdev=23360.45
     lat (nsec): min=1325, max=46407k, avg=3499.14, stdev=23410.57
    clat percentiles (nsec):
     |  1.00th=[  1944],  5.00th=[  2064], 10.00th=[  2192], 20.00th=[  2416],
     | 30.00th=[  2576], 40.00th=[  2736], 50.00th=[  2928], 60.00th=[  3120],
     | 70.00th=[  3440], 80.00th=[  3920], 90.00th=[  4704], 95.00th=[  5728],
     | 99.00th=[ 11072], 99.50th=[ 14912], 99.90th=[ 35584], 99.95th=[ 48896],
     | 99.99th=[102912]
   bw (  KiB/s): min= 3568, max=4742048, per=100.00%, avg=352369.75, stdev=42741.18, samples=2834
   iops        : min=  446, max=592756, avg=44046.22, stdev=5342.65, samples=2834
  lat (nsec)   : 500=0.01%, 750=30.26%, 1000=27.44%
  lat (usec)   : 2=19.93%, 4=16.09%, 10=3.63%, 20=0.26%, 50=0.07%
  lat (usec)   : 100=0.68%, 250=1.03%, 500=0.49%, 750=0.03%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.06%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%
  cpu          : usr=1.05%, sys=9.69%, ctx=678268, majf=0, minf=99
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=31203103,7802492,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1348MiB/s (1413MB/s), 1348MiB/s-1348MiB/s (1413MB/s-1413MB/s), io=238GiB (256GB), run=180899-180899msec
  WRITE: bw=337MiB/s (353MB/s), 337MiB/s-337MiB/s (353MB/s-353MB/s), io=59.5GiB (63.9GB), run=180899-180899msec

Storage Class: none - hostPath on Standard_D32ds_v5 (32 CPUs)
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=467MiB/s,w=115MiB/s][r=59.8k,w=14.7k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=98: Tue Jul 22 13:01:57 2025
  read: IOPS=57.3k, BW=447MiB/s (469MB/s)(78.6GiB/180001msec)
    clat (usec): min=66, max=128277, avg=136.99, stdev=400.80
     lat (usec): min=66, max=128277, avg=137.05, stdev=400.80
    clat percentiles (usec):
     |  1.00th=[  106],  5.00th=[  111], 10.00th=[  114], 20.00th=[  118],
     | 30.00th=[  121], 40.00th=[  124], 50.00th=[  126], 60.00th=[  129],
     | 70.00th=[  133], 80.00th=[  137], 90.00th=[  143], 95.00th=[  153],
     | 99.00th=[  265], 99.50th=[  437], 99.90th=[  750], 99.95th=[ 1188],
     | 99.99th=[23725]
   bw (  KiB/s): min=46032, max=510048, per=100.00%, avg=460061.96, stdev=11484.25, samples=2861
   iops        : min= 5754, max=63756, avg=57507.75, stdev=1435.53, samples=2861
  write: IOPS=14.3k, BW=112MiB/s (117MB/s)(19.7GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=2792, avg= 4.58, stdev= 5.52
     lat (usec): min=2, max=2792, avg= 4.67, stdev= 5.57
    clat percentiles (usec):
     |  1.00th=[    3],  5.00th=[    4], 10.00th=[    4], 20.00th=[    4],
     | 30.00th=[    4], 40.00th=[    4], 50.00th=[    4], 60.00th=[    5],
     | 70.00th=[    5], 80.00th=[    6], 90.00th=[    6], 95.00th=[    8],
     | 99.00th=[   12], 99.50th=[   15], 99.90th=[   47], 99.95th=[   68],
     | 99.99th=[  163]
   bw (  KiB/s): min=11424, max=136512, per=100.00%, avg=115156.24, stdev=2915.34, samples=2861
   iops        : min= 1428, max=17064, avg=14394.53, stdev=364.42, samples=2861
  lat (usec)   : 4=10.42%, 10=9.27%, 20=0.27%, 50=0.04%, 100=0.09%
  lat (usec)   : 250=79.05%, 500=0.59%, 750=0.19%, 1000=0.03%
  lat (msec)   : 2=0.02%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.01%
  lat (msec)   : 100=0.01%, 250=0.01%
  cpu          : usr=0.79%, sys=7.82%, ctx=10310143, majf=0, minf=85
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=10307066,2579840,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=447MiB/s (469MB/s), 447MiB/s-447MiB/s (469MB/s-469MB/s), io=78.6GiB (84.4GB), run=180001-180001msec
  WRITE: bw=112MiB/s (117MB/s), 112MiB/s-112MiB/s (117MB/s-117MB/s), io=19.7GiB (21.1GB), run=180001-180001msec

Disk stats (read/write):
  sdb: ios=10300362/2219104, sectors=164805792/45400496, merge=0/172, ticks=1284423/2095772, in_queue=3380195, util=71.78%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting

Jobs: 8 (f=8): [M(8)][100.0%][r=80.0MiB/s,w=19.3MiB/s][r=10.2k,w=2469 IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=140: Tue Jul 22 13:05:21 2025
  read: IOPS=216k, BW=1685MiB/s (1766MB/s)(296GiB/180016msec)
    clat (nsec): min=480, max=254172k, avg=34938.97, stdev=1130804.48
     lat (nsec): min=504, max=254172k, avg=34968.99, stdev=1130804.48
    clat percentiles (nsec):
     |  1.00th=[     604],  5.00th=[     636], 10.00th=[     660],
     | 20.00th=[     708], 30.00th=[     764], 40.00th=[     836],
     | 50.00th=[     916], 60.00th=[     988], 70.00th=[    1064],
     | 80.00th=[    1176], 90.00th=[    1416], 95.00th=[    1688],
     | 99.00th=[  193536], 99.50th=[  254976], 99.90th=[  577536],
     | 99.95th=[36438016], 99.99th=[51118080]
   bw (  MiB/s): min=   17, max=23701, per=100.00%, avg=1716.82, stdev=227.23, samples=2826
   iops        : min= 2248, max=3033850, avg=219752.77, stdev=29085.60, samples=2826
  write: IOPS=53.9k, BW=421MiB/s (442MB/s)(74.0GiB/180016msec); 0 zone resets
    clat (nsec): min=1281, max=48692k, avg=3218.22, stdev=23201.65
     lat (nsec): min=1324, max=48693k, avg=3271.57, stdev=23373.49
    clat percentiles (nsec):
     |  1.00th=[ 1960],  5.00th=[ 2096], 10.00th=[ 2192], 20.00th=[ 2352],
     | 30.00th=[ 2512], 40.00th=[ 2640], 50.00th=[ 2768], 60.00th=[ 2928],
     | 70.00th=[ 3152], 80.00th=[ 3472], 90.00th=[ 4192], 95.00th=[ 5024],
     | 99.00th=[ 9664], 99.50th=[13504], 99.90th=[36608], 99.95th=[50432],
     | 99.99th=[97792]
   bw (  KiB/s): min= 4848, max=6055360, per=100.00%, avg=439575.84, stdev=58070.42, samples=2825
   iops        : min=  606, max=756920, avg=54946.98, stdev=7258.80, samples=2825
  lat (nsec)   : 500=0.01%, 750=21.96%, 1000=27.65%
  lat (usec)   : 2=27.87%, 4=17.68%, 10=2.37%, 20=0.16%, 50=0.07%
  lat (usec)   : 100=0.72%, 250=1.10%, 500=0.34%, 750=0.02%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.05%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%
  cpu          : usr=1.19%, sys=11.71%, ctx=811054, majf=0, minf=99
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=38817645,9702489,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1685MiB/s (1766MB/s), 1685MiB/s-1685MiB/s (1766MB/s-1766MB/s), io=296GiB (318GB), run=180016-180016msec
  WRITE: bw=421MiB/s (442MB/s), 421MiB/s-421MiB/s (442MB/s-442MB/s), io=74.0GiB (79.5GB), run=180016-180016msec

Disk stats (read/write):
  sdb: ios=1082833/148326, sectors=554229136/160743840, merge=0/183, ticks=2597704/4902231, in_queue=7499936, util=83.38%

Storage Class: none - hostPath on Standard_E16pds_v5 (ARM 16 CPUs)
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=455MiB/s,w=115MiB/s][r=58.2k,w=14.7k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=84: Tue Jul 22 13:34:32 2025
  read: IOPS=50.3k, BW=393MiB/s (412MB/s)(69.1GiB/180001msec)
    clat (usec): min=73, max=40128, avg=155.11, stdev=578.03
     lat (usec): min=73, max=40128, avg=155.20, stdev=578.04
    clat percentiles (usec):
     |  1.00th=[  111],  5.00th=[  117], 10.00th=[  120], 20.00th=[  124],
     | 30.00th=[  128], 40.00th=[  131], 50.00th=[  135], 60.00th=[  137],
     | 70.00th=[  141], 80.00th=[  147], 90.00th=[  157], 95.00th=[  172],
     | 99.00th=[  277], 99.50th=[  627], 99.90th=[ 1319], 99.95th=[19530],
     | 99.99th=[23462]
   bw (  KiB/s): min=28416, max=477168, per=100.00%, avg=405117.14, stdev=14844.09, samples=2852
   iops        : min= 3552, max=59646, avg=50639.49, stdev=1855.52, samples=2852
  write: IOPS=12.6k, BW=98.4MiB/s (103MB/s)(17.3GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=1596, avg= 5.70, stdev= 5.30
     lat (usec): min=2, max=1596, avg= 5.84, stdev= 5.31
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    4], 10.00th=[    5], 20.00th=[    5],
     | 30.00th=[    5], 40.00th=[    5], 50.00th=[    5], 60.00th=[    6],
     | 70.00th=[    6], 80.00th=[    7], 90.00th=[    8], 95.00th=[   10],
     | 99.00th=[   14], 99.50th=[   17], 99.90th=[   43], 99.95th=[   69],
     | 99.99th=[  273]
   bw (  KiB/s): min= 6113, max=129504, per=100.00%, avg=101455.63, stdev=3748.86, samples=2852
   iops        : min=  764, max=16188, avg=12681.77, stdev=468.61, samples=2852
  lat (usec)   : 4=1.90%, 10=17.33%, 20=0.75%, 50=0.03%, 100=0.02%
  lat (usec)   : 250=79.08%, 500=0.37%, 750=0.20%, 1000=0.05%
  lat (msec)   : 2=0.21%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.04%
  cpu          : usr=1.04%, sys=8.67%, ctx=9058110, majf=0, minf=77
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=9050760,2266570,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=393MiB/s (412MB/s), 393MiB/s-393MiB/s (412MB/s-412MB/s), io=69.1GiB (74.1GB), run=180001-180001msec
  WRITE: bw=98.4MiB/s (103MB/s), 98.4MiB/s-98.4MiB/s (103MB/s-103MB/s), io=17.3GiB (18.6GB), run=180001-180001msec

Disk stats (read/write):
  sdb: ios=9040250/1932420, sectors=144644016/34824832, merge=0/141, ticks=1301959/3518088, in_queue=4820047, util=78.38%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=1557MiB/s,w=388MiB/s][r=199k,w=49.7k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=110: Tue Jul 22 13:39:20 2025
  read: IOPS=169k, BW=1323MiB/s (1387MB/s)(233GiB/180031msec)
    clat (nsec): min=760, max=203083k, avg=44739.99, stdev=1254001.74
     lat (nsec): min=800, max=203083k, avg=44782.94, stdev=1254001.73
    clat percentiles (nsec):
     |  1.00th=[    1080],  5.00th=[    1160], 10.00th=[    1208],
     | 20.00th=[    1240], 30.00th=[    1288], 40.00th=[    1368],
     | 50.00th=[    1400], 60.00th=[    1528], 70.00th=[    1608],
     | 80.00th=[    1720], 90.00th=[    1928], 95.00th=[    2160],
     | 99.00th=[  301056], 99.50th=[  428032], 99.90th=[ 1089536],
     | 99.95th=[35389440], 99.99th=[50593792]
   bw (  MiB/s): min=   17, max=19722, per=100.00%, avg=1343.30, stdev=160.83, samples=2829
   iops        : min= 2182, max=2524512, avg=171941.89, stdev=20586.63, samples=2829
  write: IOPS=42.3k, BW=331MiB/s (347MB/s)(58.1GiB/180031msec); 0 zone resets
    clat (nsec): min=1600, max=54275k, avg=3682.85, stdev=20244.58
     lat (nsec): min=1640, max=54275k, avg=3755.71, stdev=20327.82
    clat percentiles (nsec):
     |  1.00th=[ 2288],  5.00th=[ 2448], 10.00th=[ 2512], 20.00th=[ 2736],
     | 30.00th=[ 2896], 40.00th=[ 3056], 50.00th=[ 3216], 60.00th=[ 3376],
     | 70.00th=[ 3568], 80.00th=[ 4016], 90.00th=[ 4896], 95.00th=[ 5664],
     | 99.00th=[13376], 99.50th=[17024], 99.90th=[32640], 99.95th=[45824],
     | 99.99th=[86528]
   bw (  KiB/s): min= 3984, max=5033360, per=100.00%, avg=343955.22, stdev=41102.00, samples=2829
   iops        : min=  498, max=629170, avg=42994.40, stdev=5137.75, samples=2829
  lat (nsec)   : 1000=0.12%
  lat (usec)   : 2=73.41%, 4=19.77%, 10=3.77%, 20=0.51%, 50=0.07%
  lat (usec)   : 100=0.61%, 250=0.70%, 500=0.77%, 750=0.16%, 1000=0.02%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.06%
  lat (msec)   : 100=0.01%, 250=0.01%
  cpu          : usr=1.05%, sys=11.53%, ctx=676822, majf=0, minf=93
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=30480328,7621559,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1323MiB/s (1387MB/s), 1323MiB/s-1323MiB/s (1387MB/s-1387MB/s), io=233GiB (250GB), run=180031-180031msec
  WRITE: bw=331MiB/s (347MB/s), 331MiB/s-331MiB/s (347MB/s-347MB/s), io=58.1GiB (62.4GB), run=180031-180031msec

Disk stats (read/write):
  sdb: ios=886704/48466, sectors=453852448/116858936, merge=0/115, ticks=2623500/2928636, in_queue=5552135, util=84.47%

Storage Class: none - hostPath on Standard_D32pds_v5 (ARM 32 CPUs)	
============================================================
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=randrw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [m(8)][100.0%][r=451MiB/s,w=114MiB/s][r=57.8k,w=14.5k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=99: Tue Jul 22 14:13:14 2025
  read: IOPS=55.1k, BW=431MiB/s (452MB/s)(75.7GiB/180001msec)
    clat (usec): min=74, max=32793, avg=140.26, stdev=121.96
     lat (usec): min=74, max=32793, avg=140.41, stdev=121.96
    clat percentiles (usec):
     |  1.00th=[  115],  5.00th=[  120], 10.00th=[  123], 20.00th=[  126],
     | 30.00th=[  129], 40.00th=[  133], 50.00th=[  135], 60.00th=[  137],
     | 70.00th=[  141], 80.00th=[  145], 90.00th=[  153], 95.00th=[  167],
     | 99.00th=[  235], 99.50th=[  351], 99.90th=[  717], 99.95th=[ 1188],
     | 99.99th=[ 1532]
   bw (  KiB/s): min=102576, max=470448, per=100.00%, avg=444832.63, stdev=6068.97, samples=2848
   iops        : min=12822, max=58806, avg=55604.08, stdev=758.62, samples=2848
  write: IOPS=13.8k, BW=108MiB/s (113MB/s)(19.0GiB/180001msec); 0 zone resets
    clat (usec): min=2, max=685, avg= 5.95, stdev= 4.24
     lat (usec): min=2, max=685, avg= 6.16, stdev= 4.26
    clat percentiles (usec):
     |  1.00th=[    4],  5.00th=[    4], 10.00th=[    5], 20.00th=[    5],
     | 30.00th=[    5], 40.00th=[    5], 50.00th=[    6], 60.00th=[    6],
     | 70.00th=[    7], 80.00th=[    7], 90.00th=[    9], 95.00th=[   11],
     | 99.00th=[   15], 99.50th=[   17], 99.90th=[   45], 99.95th=[   69],
     | 99.99th=[  169]
   bw (  KiB/s): min=25152, max=128464, per=100.00%, avg=111371.73, stdev=1593.26, samples=2848
   iops        : min= 3144, max=16058, avg=13921.47, stdev=199.16, samples=2848
  lat (usec)   : 4=1.77%, 10=17.24%, 20=0.97%, 50=0.03%, 100=0.01%
  lat (usec)   : 250=79.32%, 500=0.47%, 750=0.11%, 1000=0.02%
  lat (msec)   : 2=0.06%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.01%
  cpu          : usr=1.68%, sys=10.07%, ctx=9939054, majf=0, minf=76
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=9921770,2484188,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=431MiB/s (452MB/s), 431MiB/s-431MiB/s (452MB/s-452MB/s), io=75.7GiB (81.3GB), run=180001-180001msec
  WRITE: bw=108MiB/s (113MB/s), 108MiB/s-108MiB/s (113MB/s-113MB/s), io=19.0GiB (20.3GB), run=180001-180001msec

Disk stats (read/write):
  sdb: ios=9918473/2154590, sectors=158695568/42258344, merge=0/99, ticks=1279878/2119221, in_queue=3399099, util=74.90%

------------------------------------------------------------
Command: fio --name=kvstore_test  --directory=/opt/dremio/data --direct=0 --rw=rw --rwmixread=80 --bs=8k --size=8G --numjobs=8 --iodepth=1 --ioengine=psync --runtime=180 --time_based --group_reporting
Jobs: 8 (f=8): [M(8)][100.0%][r=1857MiB/s,w=460MiB/s][r=238k,w=58.9k IOPS][eta 00m:00s]
kvstore_test: (groupid=0, jobs=8): err= 0: pid=141: Tue Jul 22 14:16:50 2025
  read: IOPS=216k, BW=1689MiB/s (1771MB/s)(297GiB/180001msec)
    clat (nsec): min=760, max=301700k, avg=34192.37, stdev=1023280.12
     lat (nsec): min=800, max=301700k, avg=34235.31, stdev=1023280.10
    clat percentiles (nsec):
     |  1.00th=[    1080],  5.00th=[    1160], 10.00th=[    1240],
     | 20.00th=[    1288], 30.00th=[    1320], 40.00th=[    1400],
     | 50.00th=[    1528], 60.00th=[    1608], 70.00th=[    1688],
     | 80.00th=[    1800], 90.00th=[    1960], 95.00th=[    2192],
     | 99.00th=[  280576], 99.50th=[  399360], 99.90th=[  716800],
     | 99.95th=[31850496], 99.99th=[47448064]
   bw (  MiB/s): min=   45, max=20593, per=100.00%, avg=1742.32, stdev=211.56, samples=2785
   iops        : min= 5852, max=2635932, avg=223016.68, stdev=27079.13, samples=2785
  write: IOPS=54.0k, BW=422MiB/s (443MB/s)(74.2GiB/180001msec); 0 zone resets
    clat (nsec): min=1600, max=54448k, avg=3623.26, stdev=23411.54
     lat (nsec): min=1640, max=54448k, avg=3698.11, stdev=23461.19
    clat percentiles (nsec):
     |  1.00th=[ 2320],  5.00th=[ 2448], 10.00th=[ 2512], 20.00th=[ 2672],
     | 30.00th=[ 2896], 40.00th=[ 3056], 50.00th=[ 3216], 60.00th=[ 3376],
     | 70.00th=[ 3568], 80.00th=[ 3920], 90.00th=[ 4832], 95.00th=[ 5536],
     | 99.00th=[11072], 99.50th=[15680], 99.90th=[33024], 99.95th=[44288],
     | 99.99th=[76288]
   bw (  KiB/s): min=11152, max=5262880, per=100.00%, avg=445947.26, stdev=54062.52, samples=2785
   iops        : min= 1394, max=657860, avg=55743.41, stdev=6757.81, samples=2785
  lat (nsec)   : 1000=0.11%
  lat (usec)   : 2=72.25%, 4=21.33%, 10=3.63%, 20=0.39%, 50=0.05%
  lat (usec)   : 100=0.60%, 250=0.70%, 500=0.73%, 750=0.14%, 1000=0.01%
  lat (msec)   : 2=0.01%, 4=0.01%, 10=0.01%, 20=0.01%, 50=0.05%
  lat (msec)   : 100=0.01%, 250=0.01%, 500=0.01%
  cpu          : usr=1.35%, sys=14.64%, ctx=827416, majf=0, minf=94
  IO depths    : 1=100.0%, 2=0.0%, 4=0.0%, 8=0.0%, 16=0.0%, 32=0.0%, >=64=0.0%
     submit    : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     complete  : 0=0.0%, 4=100.0%, 8=0.0%, 16=0.0%, 32=0.0%, 64=0.0%, >=64=0.0%
     issued rwts: total=38920227,9727993,0,0 short=0,0,0,0 dropped=0,0,0,0
     latency   : target=0, window=0, percentile=100.00%, depth=1

Run status group 0 (all jobs):
   READ: bw=1689MiB/s (1771MB/s), 1689MiB/s-1689MiB/s (1771MB/s-1771MB/s), io=297GiB (319GB), run=180001-180001msec
  WRITE: bw=422MiB/s (443MB/s), 422MiB/s-422MiB/s (443MB/s-443MB/s), io=74.2GiB (79.7GB), run=180001-180001msec

Disk stats (read/write):
  sdb: ios=1085045/67217, sectors=555361504/156299392, merge=0/132, ticks=2529912/4554535, in_queue=7084447, util=72.70%