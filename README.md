
UPTIME VM--1
$stat = 'sys.osuptime.latest'
$entity = Get-VM c4t25001
Get-Stat -Entity $entity -Stat $stat -Realtime -MaxSamples 1 -ErrorAction SilentlyContinue |
Select @{N='VM';E={$_.Entity.Name}},
@{N='Uptime (d.hh:mm:ss)';E={[timespan]::FromSeconds($_.value)}}
