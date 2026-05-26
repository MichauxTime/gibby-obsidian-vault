# RuView

## What it is
A WiFi-based spatial intelligence platform that uses Channel State Information (CSI) from $9 ESP32 sensors to detect presence, measure breathing/heart rate, and track movement through walls — no cameras, no wearables required.

## The good
- Runs entirely on edge hardware; no cloud, no internet connection required after setup
- Integrates natively with Home Assistant, Apple Home, Google Home, Alexa, and Matter — one --mqtt flag for HA
- Ships 21 entities per node including inferred states like someone-sleeping, possible-distress, and fall-risk-elevated
- Pretrained model fits in 8KB (4-bit quantized), runs sub-millisecond on a Raspberry Pi
- Ed25519 cryptographic attestation chain on every measurement — auditable sensor data
- 1,463 tests passing; multi-arch Docker image; Rust 1.85+; 10M+ downloads

## The bad
- Hardware setup required (ESP32 mesh nodes) — not a pure software solution
- The 100% presence accuracy claim is on a validation set, not independently audited real-world deployment
- Multi-person counting is still reliant on tunable dedup factors that require manual calibration per space

## Watch out for
- Through-wall sensing raises obvious privacy and legal concerns in commercial or multi-tenant spaces — occupancy data of people who haven't consented is a liability
- A ruvnet project — ruvnet repos tend to be impressively spec'd but verify active maintenance before building on top

## Top 5 use cases for us (Gibby/StreetLegal/Stylograph context)
1. Food truck event intelligence — deploy at permitted event sites to measure actual foot traffic vs. event organizer estimates without camera infrastructure
2. Stylograph pilot site engagement measurement — passive occupancy sensing in athletic facilities to correlate handwritten note campaigns with donor visit patterns
3. Smart venue compliance monitoring — detect room occupancy vs. permitted capacity without cameras for event permit audit trails
4. Fall detection + elderly inactivity anomaly alerts at community venues hosting StreetLegal target markets (farmers markets, senior-adjacent events)
5. Meeting-in-progress detection for remote work use cases if building out agent-aware workspace infrastructure

## Verdict
Watch — the technology is genuinely novel and the edge-first architecture is the right call, but validate real-world accuracy claims and sort out the privacy/consent angle before any commercial deployment.

## Source
https://github.com/ruvnet/RuView
