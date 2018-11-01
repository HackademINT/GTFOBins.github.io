---
functions:
  shell:
    - code: |
        rvim
        :diffpatch $(sh <&2 >&2)
---
