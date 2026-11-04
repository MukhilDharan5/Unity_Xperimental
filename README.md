# Unity_Xperimental

**The experimental workspace for [Unity](https://github.com/MukhilDharan5/Unity_Linux).**

Unity_Xperimental is a documentation-first repository for ideas, research, feasibility tests, and proof-of-concept implementations related to the Unity cross-device ecosystem.

This repository is **not** a production component of Unity. Experiments may be incomplete, device-specific, unstable, or ultimately abandoned. Successful ideas can be refined and integrated into the appropriate Unity project later, but integration is never assumed.

## Experiment index

| Experiment | Objective | Status | Documentation |
| --- | --- | --- | --- |
| `Android_Privilaged_Audio_Router` | Investigate routing Android call audio over a local network to a Linux computer and its connected audio devices. | Research / proof of concept | [Overview](#android_privilaged_audio_router) |

> **Status guide:** **Idea** = not investigated · **Research** = feasibility being assessed · **Proof of concept** = experimental implementation being built or tested · **Validated** = demonstrated under documented conditions · **Archived** = paused or discontinued.

## Experiments

### Android_Privilaged_Audio_Router

**Goal:** Explore whether an Android device's cellular call audio can be accessed through privileged audio paths and streamed over LAN to a Linux computer, with the possibility of sending microphone audio back to the phone for two-way calls.

**Motivation:** Allow a phone to handle the cellular connection while a Linux laptop and its connected headphones or microphone serve as the call interface.

**Initial scope:**

- Standalone Android and Linux proof of concept; **no dependency on Unity**.
- Investigate Android telephony audio policies, capture restrictions, privilege requirements, and device-specific routing behavior.
- Test Android-to-Linux audio transport and, if feasible, Linux-to-Android microphone transport.
- Document measurements, failed approaches, workarounds, security considerations, and reproducible test results.
- Consider Unity integration **only after** technical feasibility has been demonstrated.

**Known challenge:** Standard third-party Android applications generally cannot capture live cellular-call audio through ordinary recording APIs. Privileged permissions, system-level changes, or device-specific capabilities may be required, and some paths may remain blocked by the audio HAL or modem. **No working call-audio interception or bidirectional route is claimed here.**

**Current status:** Research / proof-of-concept planning. Results and implementation details should be documented in `Android_Privilaged_Audio_Router/README.md` once that experiment's folder is added.

## Repository organization

Each experiment should have its own directory, with a `README.md` describing the problem, environment, hypotheses, methods, results, limitations, and possible next steps. Source code, scripts, logs, and references belong alongside those documents when applicable.

```text
Unity_Xperimental/
├── README.md                           # Experiment index (this file)
└── Android_Privilaged_Audio_Router/    # First experiment (planned)
    ├── README.md                       # Research notes and results
    └── ...                             # Optional prototype code and test data
```

The layout above is a **proposed structure**, not a claim that the experiment files already exist.

## Experimental principles

1. **Document before integrating.** Clearly separate hypotheses, attempted approaches, and confirmed results.
2. **Keep experiments isolated.** A prototype should not require changes to the main Unity codebase unless explicitly stated.
3. **Record the environment.** Note OS versions, Android build, device, permissions, hardware, and test setup for reproducibility.
4. **Be transparent about limitations.** Report failures, unexpected behavior, latency, and device-specific requirements.
5. **Respect security and privacy.** Handle call audio and other sensitive data only with appropriate authorization and consent; avoid uploading raw captures, secrets, or personal identifiers.

## Relationship to Unity

[Unity](https://github.com/MukhilDharan5/Unity_Linux) is the main cross-device project. **Unity_Xperimental** is where uncertain ideas can be explored independently without presenting them as supported Unity features.

An experiment being listed here **does not mean** that it is functional, endorsed for everyday use, or scheduled for integration.
