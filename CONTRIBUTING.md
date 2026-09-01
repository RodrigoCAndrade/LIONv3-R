# Contribution Guidelines

As an engineering project, our development lifecycle demands strict adherence to verification, traceability, and reliability standards. Whether you are contributing to Software, Electronics, or Mechanical integration, please follow the guidelines outlined below.

## 1. Licensing and Preamble

All authored content must contain the appropriate preamble and copyright notice at the top of the file. We operate under a dual-licensing model:

*   **Software (`software/`):** MIT License.
*   **Hardware (`hardware/`, `mechanics/`):** CERN-OHL-P-2.0.

Source code files must also include a brief Doxygen-style header documenting the author, date, and description:

```
/**
 * \file filename.c
 * \brief Brief description of the module.
 * \author Author Name <author@email.com>
 * \date YYYY/MM/DD
 *
 * SPDX-License-Identifier: MIT
 */
```

## 2. Software Engineering

We prioritize deterministic, safe, and readable code suitable for embedded systems.

*   **Coding Standard:** We strongly prefer a recognized coding standard for the C Programming Language (based on MISRA-C).
*   **Documentation:** All functions must include Doxygen headings specifying `\brief`, `\param`, and `\return`.
*   **Include Guards:** All header files must implement preprocessor checking (`#ifndef FILENAME_H_`) to prevent multiple inclusions. Include dependencies only where strictly necessary.
*   **Style:** Indent with **4 spaces** (no tabs). Variable names must be lowercase and separated by underscores (`int sensor_reading = 0;`).

## 3. Hardware Engineering

Hardware contributions must maintain the integrity of the system architecture and conform to applicable physical standards.

*   **Toolchain:** Use KiCad for all schematic and PCB layout design.
*   **Rule Checks:** Before committing any PCB changes, you **must** run and clear the Electrical Rule Check (ERC) and Design Rule Check (DRC). Pull Requests with ERC/DRC violations will be rejected.
*   **Generated Files:** Do not commit manufacturing outputs (Gerbers, NC Drill, BOM) or 3D STEP files during regular development. These are generated exclusively by repository administrators during tagged release cycles to prevent synchronization issues.
*   **Self-Contained Libraries:** To ensure 100% reproducibility and prevent missing dependencies, every hardware repository must be entirely self-contained. All symbols, footprints, and 3D models must be stored within project-specific local libraries (e.g., .kicad_sym, .kicad_mod) inside the repository. Never link to global, external, or user-specific machine libraries.

## 4. Verification and Testing

No code or hardware design is merged without proven verification.

*   **Traceability:** Every Pull Request (PR) must reference a specific System Requirement (SRD) or an open Issue.
*   **Testing:** Software PRs must include unit tests or hardware-in-the-loop validation logs. Hardware PRs must include physical integration checks or thermal/electromagnetic simulation results if applicable.

## 5. Git Flow and Branching Strategy

We utilize a segmented Git workflow to isolate disciplines and maintain a stable production environment.

### Core Branches
*   `main`: **Production Model (PM).** Contains only tested, stable, and production-ready releases.
*   `dev`: **Integration / Development Model (DM).** The staging branch where all disciplines merge their validated work.

### Segment Branches
Regular development occurs in discipline-specific branches:
*   `dev_hardware`
*   `dev_software`
*   `dev_mechanics`
*   `dev_tests`

### Workflow
1. Create a feature branch originating from the relevant segment branch (e.g., `feature/eps-telemetry` from `dev_software`).
2. Commit your changes with clear, descriptive messages.
3. Open a Pull Request (PR) against the segment branch.
4. The PR requires review and approval from repository administrators before being merged. Merges to `dev` and `main` are handled exclusively by maintainers after integration tests.
