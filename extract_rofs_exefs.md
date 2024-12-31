# Extract ROFS / ExeFS

## Prerequisites
- ctrtool Latest Release - https://github.com/3DSGuy/Project_CTR/releases (DO NOT download a "MakeROM" release from this page)
- rofs_dumper - https://github.com/PabloMK7/rofs_dumper/releases
    - MacOS and Linux releases are not available, so building from source will be required if using one of those platforms. Consult the readme of rofs_dumper for more information.

## Extracting romfs (rofs)

Titles from this stage of the 3DS's development use an earlier romfs format known as "ROFS".

1. Run `ctrtool -d --romfs=rofs.bin 00000000.app`. It will produce an error, but the file will be created successfully.
2. Run `rofs_dump rofs.bin output_folder_name_here`.

## Extracting exefs

Run `ctrtool -d --exefs=exefs.bin 00000000.app`. It will produce an error, but the file will be created successfully.
