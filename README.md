# Assistive Voice Generator App

A mobile augmentative and alternative communication (AAC) app that helps people without vocal cords, or with severe speech difficulty, communicate quickly through their phone.

[![Flutter](https://img.shields.io/badge/framework-Flutter-02569B.svg)](https://flutter.dev/)
[![Platform](https://img.shields.io/badge/platform-Android-3DDC84.svg)](https://developer.android.com/)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)

▶️ **Demo video:** [youtu.be/BlwuTGTi4sI](https://youtu.be/BlwuTGTi4sI)

## Table of contents

- [Overview](#overview)
- [Problem statement](#problem-statement)
- [Key features](#key-features)
- [Target users](#target-users)
- [Tech stack](#tech-stack)
- [Project structure](#project-structure)
- [Getting started](#getting-started)
- [Team & context](#team--context)
- [Why this matters](#why-this-matters)
- [Limitations & future work](#limitations--future-work)
- [License](#license)
- [Contact](#contact)

## Overview

Each year, roughly 700 people in Taiwan are diagnosed with throat cancer, and many who undergo vocal cord removal surgery lose the ability to speak naturally afterward. Most patients in this group are aged 50–70, a generation for which Taiwanese (Hokkien) is a primary spoken language — yet no voice assistant app at the time supported it. This app lets people with no vocal cords or significant speech difficulty communicate through their phone: quick-reply shortcuts for common phrases, manual text input for anything else, and a floating alert button so a caregiver can be reached immediately.

The project was developed in collaboration with a laryngeal/throat-cancer patient, who recorded roughly 20 hours of read text — with informed consent — so a personalized voice model could be trained from their own voice. Voice synthesis itself is handled by an API built by a research collaborator using a knowledge-graph-based training approach; this app's contribution is the end-to-end patient-facing experience: the recording workflow, the shortcut/manual-input interface, and the caregiver alert system built around that voice model.

## Problem statement

- Laryngectomy and other vocal-cord-removal patients regain the ability to *think* and *type* a message, but not to speak one.
- Most mainstream AAC and text-to-speech apps are built around English or Mandarin, leaving a real gap for Taiwanese-speaking patients.
- Caregivers need a fast, low-friction way to be alerted when the patient needs help — not a multi-step menu.

## Key features

- **Personalized voice synthesis** — spoken output uses a voice model trained from ~20 hours of a collaborating patient's own recordings (built by a research collaborator, integrated via API), rather than a generic system voice.
- **Shortcut phrases** — one-tap access to frequently needed sentences for immediate response.
- **Manual text input** — type any message and have it spoken aloud on demand, in the patient's trained voice.
- **Floating alert button** — a persistent, always-reachable control that signals a caregiver, independent of which screen or app is open.
- **Taiwanese (Hokkien) language support** — addressing a demographic largely underserved by existing voice-assistant apps.

## Target users

- People recovering from laryngectomy or other vocal-cord-removal surgery
- Anyone with a speech impairment that makes verbal communication difficult
- Family members and caregivers who need to respond quickly to alerts

## Tech stack

| Layer | Tools |
|---|---|
| Framework | Flutter (Dart) |
| IDE | Android Studio |
| Target platform | Android (phone & tablet) |
| Voice model | Personalized voice synthesis via an API built by a research collaborator, using a knowledge-graph-based voice-training approach |
| Speech output | App calls the voice-model API and plays back the synthesized audio; Android text-to-speech (TTS) as fallback/for shortcuts |
| Testing environment | Windows 10 host, physical Android tablet & phone, Android Virtual Device (AVD) |

## Project structure

```text
AssistiveVoiceGeneratorApp/
├── work/     # Application source and working files
├── Award/    # Materials related to competitions / recognition this project received
├── .idea/    # Android Studio / IntelliJ project settings
├── LICENSE   # All rights reserved — demonstration only
└── README.md
```

> This overview reflects the top-level layout only. If the Flutter project itself lives in a subfolder (e.g. `work/`), `cd` into it before running the Flutter commands below — update this section with the exact path once you finalize the repo layout.

## Getting started

```bash
git clone https://github.com/hao8359/AssistiveVoiceGeneratorApp.git
cd AssistiveVoiceGeneratorApp   # or into the subfolder containing pubspec.yaml, if applicable
flutter pub get
flutter run
```

Requires the [Flutter SDK](https://docs.flutter.dev/get-started/install) and either a connected Android device or a configured AVD emulator.

## Team & context

This was originally developed as a university research/course project.

- **Research topic:** Voice Assistant App — Daily Life and Medical Applications
- **Advisor:** Professor Wen-Hsiang Lu
- **Team:** De-Chi Hao, Yan Zhou

## Why this matters

Augmentative and alternative communication (AAC) tools are an active, growing area of assistive technology — the field includes companies such as Stockholm-headquartered **Tobii Dynavox**, a global leader in communication aids for people who cannot speak reliably with their own voice. This project sits in the same problem space at a smaller, more focused scale: giving people who have lost the ability to speak a fast, reliable way to be heard, with attention to a language community that mainstream tools often overlook.

## Limitations & future work

- Language support currently centers on Taiwanese and Mandarin; broadening to other languages (e.g. English, Swedish) would extend the app's reach.
- No formal accessibility audit (e.g. against WCAG) has been documented yet — a natural next step for a tool built for users with disabilities.
- Real-world validation is currently a single case study — one collaborating patient recorded roughly 20 hours of text to train their personalized voice model. This demonstrates feasibility but has not been tested across a broader clinical patient group; expanding to more patients (and studying how much recorded data a new voice model actually needs) is a natural next step.
- Voice recordings and any derived voice model are personal, potentially biometric data; recordings were made with the patient's informed consent. If this project continues or works with additional patients, keep consent, retention, and deletion practices formalized and in line with applicable regulation (e.g. GDPR).

## License

This repository is shared for portfolio and demonstration purposes only. All rights are reserved — see the [`LICENSE`](LICENSE) file for details. Reuse beyond viewing the source requires prior written consent from the copyright holders.

## Contact

**Author:** De-Chi Hao ([@hao8359](https://github.com/hao8359)) 
