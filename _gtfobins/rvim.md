---
functions:
  shell:
    - code: |
        rvim
        :diffpatch $(sh <&2 >&2)
    - description: if `:python` doesn't work, also check for `:python3`. There's also `:pyfile`.
      code: |
        rvim
        :python import pty; pty.spawn("/bin/bash")
      
---
