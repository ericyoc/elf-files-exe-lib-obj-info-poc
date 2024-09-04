# ELF File Generator and Parser

This Python script generates ELF (Executable and Linkable Format) files for different types (executable, shared, and object) and versions (32-bit and 64-bit). It also parses these generated files to extract information about their headers and program segments.

## Motivating Articles and Related Work
Pratomo, B.A., Kosim, S.A., Studiawan, H., Prabowo, A.O. (2024). BarongTrace: A Malware Event Log Dataset for Linux. In: Barolli, L. (eds) Advanced Information Networking and Applications. AINA 2024. Lecture Notes on Data Engineering and Communications Technologies, vol 202. Springer, Cham. https://doi.org/10.1007/978-3-031-57916-5_5

Mohammed Rauf Ali Khan. A Utility-Based Sequential Approach for ELF Malware Analysis. Authorea. February 04, 2024. DOI: 10.22541/au.170708904.45762903/v1
https://www.authorea.com/users/723310/articles/708350-a-utility-based-sequential-approach-for-elf-malware-analysis

In-depth: ELF - The Extensible & Linkable Format YouTube https://www.youtube.com/watch?v=nC1U1LJQL8o

ELF 101 https://github.com/corkami/pics/blob/28cb0226093ed57b348723bc473cea0162dad366/binary/elf101/elf101-64.svg

OSDev.org ELF Ref: https://wiki.osdev.org/ELF

Executable and Linkable Format Ref: https://en.wikipedia.org/wiki/Executable_and_Linkable_Format

### Importance for a Malware Analyst

Understanding the structure and characteristics of ELF binaries is crucial for malware analysts for several reasons:

1. **Detection and Classification**: Knowing the different types of ELF files (executables, shared libraries, object files) helps in identifying and classifying malware samples.
2. **Behavior Analysis**: ELF header and program header information can provide insights into the behavior of the binary, such as its entry point address and memory layout.
3. **Static Analysis**: Analyzing ELF headers and segments statically can reveal important details about the binary's functionality, potential vulnerabilities, and malicious intent.
4. **Dynamic Analysis**: Understanding ELF structure aids in setting up dynamic analysis environments to observe the behavior of malware during execution.
5. **Forensic Analysis**: ELF header data can be used during forensic investigations to trace the origin and purpose of a malicious binary.

### Obfuscation, Anti-Analysis, and Evasion Techniques

Malware authors may employ various techniques to obfuscate, evade detection, and thwart analysis of ELF binaries, including:

1. **Code Obfuscation**: Techniques such as code packing, encryption, and polymorphism are used to obscure the binary's functionality and evade signature-based detection.
2. **Anti-Debugging**: Malware may employ anti-debugging techniques to detect and thwart dynamic analysis attempts by monitoring debugger-related signals or system calls.
3. **Anti-Emulation**: Some malware may detect virtualized or emulated environments and alter their behavior to avoid detection by sandboxing or emulation-based analysis tools.
4. **Rootkitting**: Advanced malware may attempt to hide its presence and evade detection by modifying system calls, kernel data structures, or the ELF binary itself.
5. **Dynamic Loading**: Malicious ELF binaries may dynamically load additional code or payloads at runtime to evade static analysis and detection by security tools.

### Motivations for Manipulating ELF Binaries

Malware authors manipulate ELF binaries for various reasons, including:

1. **Stealth and Persistence**: Modifying ELF binaries allows malware to remain undetected by security mechanisms and persistently execute on compromised systems.
2. **Payload Delivery**: Malicious payloads can be injected into legitimate ELF binaries to deliver and execute additional malware components or payloads.
3. **Privilege Escalation**: Manipulating ELF binaries can enable malware to escalate privileges, gain root access, and perform unauthorized actions on the system.
4. **Data Theft and Espionage**: Malware may manipulate ELF binaries to exfiltrate sensitive data, such as login credentials, financial information, or intellectual property.
5. **Botnet Recruitment**: Compromised ELF binaries can be used to recruit infected systems into botnets for carrying out coordinated attacks, distributed denial-of-service (DDoS) attacks, or cryptocurrency mining.

## ELF File
![](https://github.com/ericyoc/elf-files-exe-lib-obj-info-poc/blob/main/elf_file.jpg)

## ELF File Generator and Parser Generated Files

- ELF file created and saved as 'executable_32.bin'.
- ELF file created and saved as 'shared_32.bin'.
- ELF file created and saved as 'object_32.bin'.
- ELF file created and saved as 'executable_64.bin'.
- ELF file created and saved as 'shared_64.bin'.
- ELF file created and saved as 'object_64.bin'.

## ELF File Generator and Parser Parsed Information

### Executable_32.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 1           | 1=ELF32                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 2           | 2=executable                   |
| Machine                           | 3           | 3=386                          |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0x1000      | 4096                           |
| Program header offset             | 52          | 52                             |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 52          | 52                             |
| Size of program headers           | 32          | 32                             |
| Number of program headers         | 1           | 1                              |
| Size of section headers           | 40          | 40                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 32-bit executable ELF file.

### Shared_32.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 1           | 1=ELF32                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 3           | 3=shared                       |
| Machine                           | 3           | 3=386                          |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0           | 0                              |
| Program header offset             | 52          | 52                             |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 52          | 52                             |
| Size of program headers           | 32          | 32                             |
| Number of program headers         | 1           | 1                              |
| Size of section headers           | 40          | 40                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 32-bit shared library ELF file.

### Object_32.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 1           | 1=ELF32                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 1           | 1=object                       |
| Machine                           | 3           | 3=386                          |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0           | 0                              |
| Program header offset             | 0           | 0                              |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 52          | 52                             |
| Size of program headers           | 32          | 32                             |
| Number of program headers         | 0           | 0                              |
| Size of section headers           | 40          | 40                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 32-bit object ELF file.

### Executable_64.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 2           | 2=ELF64                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 2           | 2=executable                   |
| Machine                           | 62          | 62=x86_64                      |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0x1000      | 4096                           |
| Program header offset             | 64          | 64                             |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 64          | 64                             |
| Size of program headers           | 56          | 56                             |
| Number of program headers         | 1           | 1                              |
| Size of section headers           | 64          | 64                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 64-bit executable ELF file.

### Shared_64.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 2           | 2=ELF64                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 3           | 3=shared                       |
| Machine                           | 62          | 62=x86_64                      |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0           | 0                              |
| Program header offset             | 64          | 64                             |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 64          | 64                             |
| Size of program headers           | 56          | 56                             |
| Number of program headers         | 1           | 1                              |
| Size of section headers           | 64          | 64                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 64-bit shared library ELF file.

### Object_64.bin

#### ELF Header

| Field                             | Value       | Description                    |
|-----------------------------------|-------------|--------------------------------|
| Magic                             | b'\x7fELF'  | ELF Magic Number               |
| Class                             | 2           | 2=ELF64                        |
| Data                              | 1           | 1=Little Endian                |
| Version                           | 1           | 1=Current                      |
| OS/ABI                            | 0           | 0=System V                     |
| ABI Version                       | 0           | 0                              |
| Type                              | 1           | 1=object                       |
| Machine                           | 62          | 62=x86_64                      |
| Version                           | 0x1         | 1                              |
| Entry point address               | 0           | 0                              |
| Program header offset             | 0           | 0                              |
| Section header offset             | 0           | 0                              |
| Flags                             | 0           | 0                              |
| Size of this header               | 64          | 64                             |
| Size of program headers           | 56          | 56                             |
| Number of program headers         | 0           | 0                              |
| Size of section headers           | 64          | 64                             |
| Number of section headers         | 0           | 0                              |
| Section header string table index | 0           | 0                              |

#### Program Header

| Field            | Value (Hex) | Value (Decimal) | Description                  |
|------------------|-------------|-----------------|------------------------------|
| Type             | 0x1         | 1               | Type of segment              |
| Flags            | 0x7         | 7               | Segment flags (permissions)  |
| Offset           | 0x0         | 0               | Offset in the file           |
| Virtual Address  | 0x1000      | 4096            | Virtual address in memory    |
| Physical Address | 0x1000      | 4096            | Physical address in memory   |
| File Size        | 0x1000      | 4096            | Size of the segment in file  |
| Memory Size      | 0x1000      | 4096            | Size of the segment in memory|
| Alignment        | 0x1000      | 4096            | Alignment of the segment     |

#### String Data

This is a 64-bit object ELF file.

### Disclaimer

This code is for education and research purposes only.

## License
Copyright 2024 Eric Yocam

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
