# Simulation Scenarios

This directory contains the implementation files used to evaluate latency-critical network technologies in autonomous driving platooning scenarios.

The project focuses on emergency braking situations where a leading autonomous vehicle suddenly brakes and following vehicles must receive the emergency message quickly and reliably. Each scenario compares two different network configurations to analyze how TSN, DetNet, and 5G URLLC affect delay, packet delivery, wireless reliability, and collision avoidance.

## Directory Structure

```text
simulation/
├── scenario-1-wired-baseline-vs-tsn/
│   ├── wired-baseline/
│   │   └── run_wired_baseline_platoon.py
│   └── tsn/
│       └── run_tsn_platoon.py
│
├── scenario-2-tsn-only-vs-tsn-detnet/
│   ├── tsn-only/
│   │   └── run_tsn_only_wired_failure.py
│   └── tsn-detnet/
│       └── run_tsn_detnet_wired_failure.py
│
├── scenario-3-wireless-baseline-vs-urllc/
│   ├── wireless-baseline/
│   │   └── run_wireless_baseline_failure_platoon.py
│   └── urllc/
│       └── run_urllc_wireless_failure_platoon.py
│
└── scenario-4-overall-baseline-vs-integrated-lcn/
    ├── overall-baseline/
    │   └── run_overall_baseline_combined_failure.py
    └── integrated-lcn/
        └── run_integrated_lcn_combined_failure.py