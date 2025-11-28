# AES_128bit_Encryption_Decryption_In_Verilog
AES-128 Encryption &amp; Decryption in Verilog HDL. Implements full 128-bit AES with key expansion, S-box, encryption, and decryption modules. Testbench included for functional verification. Synthesizable design suitable for FPGA/ASIC. Ideal for learning AES hardware implementation or integrating into secure hardware projects.

---

# AES-128 Bit Encryption & Decryption in Verilog

![AES Logo](https://github.com/Yarok14Technologies/yarok14/blob/main/AES_(Rijndael)_Round_Function.png)

## Overview

This project implements the **Advanced Encryption Standard (AES)** with a **128-bit key** in **Verilog HDL**. The design supports both **encryption** and **decryption** operations and is suitable for FPGA or ASIC implementation.

AES-128 is a symmetric key block cipher that encrypts and decrypts data in **128-bit blocks** using a **128-bit key** over **10 rounds**. This implementation is designed for hardware efficiency and can be used for educational purposes or as a starting point for secure hardware designs.

---

## Features

* **AES-128 Bit Encryption**
* **AES-128 Bit Decryption**
* Fully written in **Verilog HDL**
* Modular and synthesizable design
* Testbench provided for functional verification
* Parameterizable for future extension to AES-192/256

---

## File Structure

```
AES_Verilog/
│
├── RTL/                             # All Verilog RTL modules
│   ├── aes128/                      # AES-128 bit modules
│   │   ├── main_encryption128.v
│   │   ├── main_decryption128.v
│   │   ├── round_keys.v
│   │   ├── mix_column.v
│   │   ├── shift_row.v
│   │   ├── substitution_box.v
│   │   └── substitution_byte.v
│   │
│   ├── aes512/                      # AES-512 bit modules
│   │   ├── AES_encryption_512.v
│   │   └── AES_decryption_512.v
│   │
│   └── testbench/                   # Testbenches for verification
│       ├── testbench_aes128.v
│       └── testbench_modified_aes512.v
│
├── sim/                             # Simulation-related files
│   └── waveform/                    # Simulation waveforms (optional)
│
├── docs/                            # Documentation
│   ├── Advanced Encryption Standard (AES).pdf
│   └── A Design Implementation and Comparative Analysis of Advanced Encryption Standard (AES) Algorithm.pdf
│
└── README.md


```

---

## Design Modules

| Module            | Description                                          |
| ----------------- | ---------------------------------------------------- |
| `aes_core.v`      | Top-level module connecting encryption & decryption  |
| `aes_encrypt.v`   | Implements AES-128 encryption logic                  |
| `aes_decrypt.v`   | Implements AES-128 decryption logic                  |
| `key_expansion.v` | Generates round keys from the main 128-bit key       |
| `sbox.v`          | Substitution box (S-box) used in AES transformations |

---

## Usage

### Simulation

1. Open your preferred Verilog simulator (Icarus Verilog, ModelSim, Vivado, etc.)
2. Compile the RTL and testbench:

   ```bash
   iverilog -o aes_tb rtl/*.v tb/tb_aes.v
   ```
3. Run simulation:

   ```bash
   vvp aes_tb
   ```
4. View waveforms using GTKWave:

   ```bash
   gtkwave sim/waveform/aes.vcd
   ```

### Synthesis

* The design is synthesizable and can be implemented on **FPGA** platforms.
* Use your FPGA toolchain to synthesize and map the RTL to the target device.

---

## Example

**Test Vector:**

```
Plaintext : 00112233445566778899aabbccddeeff
Key       : 000102030405060708090a0b0c0d0e0f
Ciphertext: 69c4e0d86a7b0430d8cdb78070b4c55a
```

The testbench verifies encryption produces the correct ciphertext and decryption returns the original plaintext.

---

## References

* [FIPS 197 – Advanced Encryption Standard (AES)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf)
* [AES Algorithm Wikipedia](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)
* Verilog HDL tutorials and FPGA design guides

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Author

**Yarok14 Technologies** – [GitHub Profile](https://github.com/Yarok14Technologies)

---


