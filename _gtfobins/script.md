---
functions:
  shell:
    - code: |
        TF=$(mktemp)
        chmod +x $TF
        script -c /bin/sh $TF
---
