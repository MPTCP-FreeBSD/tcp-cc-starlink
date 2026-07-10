# TCP CC Starlink

iperf3 congestion control (CCA) measurement logs collected over Starlink LEO satellite links across six global test locations.

## Locations

London, Mumbai, Ohio, São Paulo, Sydney, Tokyo

## Congestion Control Algorithms

BBR, BBRv1, BBRv2, CCP (Copa), Cubic, Hybla, LEOcc, PCC, Vegas

## Structure

```
downlink-sequential-logs/
  <City>/
    iperf3-downlink-sequential-logs/
      <cca>_<City>__REV_run<N>.json

uplink-sequential-logs/
  <City>/
    <cca>_<City>__FWD_run<N>.json
```

- **REV** = downlink (server → client)
- **FWD** = uplink (client → server)
- **run1–run10** = 10 repeated iperf3 runs per CCA per location per direction

## Data Format

Each `.json` file is raw iperf3 output for a single run, containing per-interval throughput, RTT, congestion window, and retransmission statistics.

## Notes

- Data collected sequentially (one CCA at a time, not run concurrently) unless noted otherwise in a given batch.
- File naming follows the pattern `<cca>_<location>__<direction>_run<number>.json`.
