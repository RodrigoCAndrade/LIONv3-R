<div align="center">
  <img src="https://framerusercontent.com/images/zX3lmokKbWs01tG0gns0ruBgLo.png" alt="Rodrigo Andrade Logo" width="96"/>
</div>

<h1 align="center">LIONv3-R Module</h1>

<p align="center">
    <a href="https://github.com/RodrigoCAndrade/LIONv3-R"><img alt="Status" src="https://img.shields.io/badge/Status-In Development-050505?style=for-the-badge"></a>
    <a href="https://github.com/RodrigoCAndrade/LIONv3-R/releases"><img alt="GitHub Release" src="https://img.shields.io/github/v/release/RodrigoCAndrade/LIONv3-R?style=for-the-badge&color=050505&logo=github&logoColor=white"></a>
    <a href="https://github.com/RodrigoCAndrade/LIONv3-R/issues"><img alt="GitHub Issues" src="https://img.shields.io/github/issues/RodrigoCAndrade/LIONv3-R?style=for-the-badge&color=050505&logo=github&logoColor=white"></a>
    <a href="https://github.com/RodrigoCAndrade/LIONv3-R/pulls"><img alt="GitHub Pull Requests" src="https://img.shields.io/github/issues-pr/RodrigoCAndrade/LIONv3-R?style=for-the-badge&color=050505&logo=github&logoColor=white"></a>
    <a href="https://github.com/RodrigoCAndrade/LIONv3-R/graphs/contributors"><img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/RodrigoCAndrade/LIONv3-R?style=for-the-badge&color=050505&logo=github&logoColor=white"></a>
</p>

<br>

<p align="center">
    <img src="mechanics/3d_exports/PCB-Front.png" width="350"><img src="mechanics/3d_exports/PCB-Back.png" width="350">
</p>

## Overview

The LIONv3-R is an IoT and Direct-to-Satellite (DtS) board built around the ESP32-C6, with 16 MB of external flash and local connectivity over Wi-Fi, Zigbee and Thread. Its radio supports LR-FHSS alongside conventional LoRa, enabling reliable uplinks to satellites or terrestrial gateways from remote sites, at device densities conventional LoRa cannot sustain. By bridging local wireless networks with satellite reach, the LIONv3-R is a complete, scalable hardware platform for telemetry, global asset tracking and remote sensing.

## Repository Organization

* `docs`: Systems engineering, datasheets, requirements (SRD), and interface control (ICD).
* `hardware`: Native KiCad project, schematics, and manufacturing files.
* `mechanics`: 3D models, technical drawings, and physical integration constraints.
* `software`: Embedded firmware and support testing scripts.

## Releases

<table>
  <thead>
    <tr>
      <th>Render</th>
      <th>Hardware Revision</th>
      <th>Status</th>
      <th>Latest Release</th>
      <th>Date</th>
      <th>Datasheet</th>
      <th>BOM</th>
      <th>Manufacturing Info</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><img src="mechanics/3d_exports/PCB-Front.png" alt="board render" width="128"/></td>
      <td>LIONv3-R</td>
      <td>🚧 Development</td>
      <td><a href="#">-</a></td>
      <td>18-08-2026</td>
      <td><a href="#">PDF</a></td>
      <td>-</td>
      <td><a href="#">Gerber</a></td>
    </tr>
  </tbody>
</table>

## Contributing

We welcome contributions to this project! To ensure a smooth collaboration and maintain our engineering standards, please review our [Contribution Guidelines](CONTRIBUTING.md) before opening any issues, modifying the hardware design, or submitting pull requests.


## References

This board was developed from scratch, but draws on the earlier LIONv1 and LIONv2 designed by [Diego Anestor Coutinho](https://github.com/DIEGOVZK) and [Arielli Ajudarte](https://github.com/ari-aju). The v3 introduces several improvements:

- Dedicated low-power MCU on board
- LR-FHSS support and a more capable LoRa transceiver, covering both sub-GHz and S-band
- External flash for store-and-forward applications
- More efficient antenna
- More compact form factor

## License

This project utilizes a dual-licensing approach to maximize flexibility and adoption:

* **Hardware:** The hardware designs and schematics are licensed under the permissive **[CERN-OHL-P-2.0](hardware/LICENSE)** open-hardware license. You are entirely free to use, modify, distribute, and commercialize the design without any copyleft obligations to share your derived works under the same terms.
* **Software:** All embedded firmware and utility scripts are licensed under the **[MIT License](software/LICENSE)**. You are free to use, modify, and distribute the code without restriction, provided the original copyright notice and permission notice are included.
