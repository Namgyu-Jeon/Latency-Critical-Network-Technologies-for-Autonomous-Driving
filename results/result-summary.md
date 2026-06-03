# Simulation Result Summary

This document summarizes the main simulation results of the project.

## Simulation 1: Wired Baseline vs TSN

This simulation compared a normal wired baseline network with a TSN-applied network under a stable environment without packet loss.

| Metric | Baseline | TSN | Improvement |
|---|---:|---:|---:|
| Average Delay | 0.628 ms | 0.082 ms | 87% reduction |
| Delay Standard Deviation | High | Low | More stable transmission |
| Average Jitter | High | Low | Reduced jitter |

### Collision Result by Vehicle Gap

| Vehicle Gap | Baseline | TSN |
|---:|---|---|
| 10 m | Crash | Crash |
| 15 m | Crash | Crash |
| 20 m | Crash | Safe |
| 25 m | Crash | Safe |
| 30 m | Crash | Safe |

### Key Finding

TSN reduced both delay and jitter for critical traffic. As a result, the TSN environment maintained safe vehicle behavior from a 20 m gap, while the baseline environment still resulted in crashes.

---

## Simulation 2: TSN Only vs TSN + DetNet

This simulation compared TSN-only communication with TSN + DetNet under packet loss conditions.

| Metric | TSN Only | TSN + DetNet |
|---|---|---|
| Average Delay | Baseline | More reduced |
| Delay Standard Deviation | Baseline | Reduced |
| Average Jitter | Baseline | Approximately 35% reduced |

### Collision Result by Vehicle Gap

| Vehicle Gap | TSN Only | TSN + DetNet |
|---:|---|---|
| 15 m | Crash | Crash |
| 17 m | Crash | Crash |
| 19 m | Crash | Crash |
| 21 m | Crash | Safe |
| 23 m | Crash | Safe |
| 25 m | Crash | Safe |

### Key Finding

TSN improves fast and predictable delivery, but it cannot recover a packet once the packet is lost. DetNet complements TSN by replicating critical messages over multiple paths, improving reliability under packet loss conditions.

---

## Simulation 3: Wireless Baseline vs URLLC

This simulation compared a wireless baseline environment with a URLLC-applied wireless environment under wireless packet loss conditions.

### Collision Result by Vehicle Gap

| Vehicle Gap | Wireless Baseline | URLLC |
|---:|---|---|
| 15 m | Crash | Crash |
| 17 m | Crash | Crash |
| 19 m | Crash | Crash |
| 21 m | Crash | Crash |
| 23 m | Crash | Safe |
| 25 m | Crash | Safe |

### Key Finding

The wireless baseline environment failed to maintain safe behavior even at larger vehicle gaps. URLLC improved wireless communication reliability and enabled safe behavior from a 23 m vehicle gap.

---

## Simulation 4: Overall Baseline vs Integrated LCN

This simulation compared an overall wired-wireless baseline environment with an integrated latency-critical network environment using TSN, DetNet, and URLLC under extreme failure conditions.

### Collision Result by Vehicle Gap

| Vehicle Gap | Overall Baseline | Integrated LCN |
|---:|---|---|
| 15 m | Crash | Crash |
| 17 m | Crash | Crash |
| 19 m | Crash | Crash |
| 21 m | Crash | Crash |
| 23 m | Crash | Safe |
| 25 m | Crash | Safe |

### Key Finding

The integrated LCN approach combined the strengths of TSN, DetNet, and URLLC. It achieved safe behavior from a 23 m vehicle gap even under extreme wired and wireless failure conditions.

---

## Overall Conclusion

The simulation results show that latency-critical network technologies are not only performance-enhancing mechanisms. They directly contribute to autonomous driving safety by reducing delay, stabilizing jitter, preventing packet loss, and improving wireless communication reliability.

---

## Raw Result Files

The raw CSV result files are available in [`results/raw/`](raw/).

These files include spacing-based collision results, minimum gap values, final gap values, receiver lists, reaction maps, and scenario end reasons for each simulation configuration.