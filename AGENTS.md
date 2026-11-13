# NextDNS Configuration Guide

## Project Overview
This repository serves as a comprehensive guide for configuring **NextDNS** to optimize for security, privacy, and usability. It provides detailed recommendations on various settings, blocklists, and allowlists, balancing strong protection with the "grandma test" (ensuring the internet remains usable for non-technical users).

**Primary Goal:** To provide a set-and-forget NextDNS configuration that prevents overblocking while maximizing privacy and security.

## Directory Overview

*   **`README.md`**: The core documentation and guide. It contains all the recommended settings, explanations for each choice, and links to external resources. It is the primary artifact of this project.
*   **`icons/`**: A directory containing SVG icons (`enabled.svg`, `disabled.svg`, etc.) used within the `README.md` to visually represent the recommended state of each NextDNS setting.
*   **`.github/`**: Contains GitHub-specific configuration files, including issue templates for bug reports and feature requests.

## Key Concepts
*   **Law of Diminishing Returns**: The guide advocates for "sane" blocklists and settings that provide the most benefit without excessive breakage.
*   **Grandma Test**: A guiding principle ensuring that the configuration does not break common websites or services, making it suitable for general use.
*   **Security & Privacy**: The guide covers Threat Intelligence, Safe Browsing, various protection mechanisms (Cryptojacking, DNS Rebinding, etc.), and privacy blocklists (recommending Hagezi's lists).

## Usage
This project is intended to be read as a manual. Users should:
1.  Create a NextDNS account.
2.  Follow the sections in `README.md` (Security, Privacy, Parental Control, Settings) to configure their NextDNS profile.
3.  Use the recommended **Blocklists** (specifically Hagezi's Multi PRO or NORMAL) and **Allowlists** provided in the guide.
