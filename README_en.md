
[中文](README.md) | [English](README_en.md)

- # AndroidApexTools

  A tool to help unpack and repack Android apex packages

  > Project address: https://github.com/wcedla/AndroidApexTools

  ## **Features**

  > Currently only supports Linux and WSL subsystem, tested on Ubuntu 22.04 in WSL2 on Win10

  ### **1. Unpack**

  ```shell
  cd path/to/script
  sudo python3 ./deapexer.py extract ./foo.apex
  ```

  After unpacking, manifest and payload folders will be generated under the script path. The manifest folder contains metadata that usually doesn't need modification. The payload folder contains the extracted img files from the original apex, which can be modified.

  ### **2. Repack**

  ```shell
  cd path/to/script
  sudo python3 ./apexer.py --api 33 ./bar.apex
  ```

  Make sure there are manifest and payload folders under the current path. The api parameter specifies the Android api version for this apex and is required.

  > Note: The repacked apex will have a different signature from the system signature and needs core patch to work.
