# Zest_Interface_Ethernet

Zest_Interface_Ethernet board support for Zephyr OS.

## Usage

This board enables the following interfaces:

- [Microchip ENC424J600](https://www.microchip.com/en-us/product/enc624j600) Ethernet controller.

:pushpin: This shield defines:

- an ethernet controller device: `enc424j600_zest_interface_ethernet_<port>`

:triangular_ruler: To use this shield:

- Update your device tree by adding the `ZEST_INTERFACE_ETHERNET(port)` macro to the `app.overlay` file.\
  Replace `port` with the number of the Zest_Core port to which the shield is connected, e.g.:

  ```c
  ZEST_INTERFACE_ETHERNET(1) /* Zest_Display_LCD connected to Zest_Core first port */
  ```

- Activate support for the shield by adding `--shield zest_interface_ethernet` to the west command.

## Advanced Usage

This shield can be hardware-modified to suit your application.

In that case, use instead the alternate variant of the shield:

- Update your device tree by adding the `ZEST_INTERFACE_ETHERNET_ALT(port, nss, irq)` macro to the `app.overlay` file, with:
  - `port`: number of the Zest_Core port to which the shield is connected,
  - `nss`: ethernet controller SPI Slave Select pin,
  - `irq`: ethernet controller IRQ pin.
- Activate support for the shield by adding `--shield zest_interface_ethernet_alt` to the west command.
