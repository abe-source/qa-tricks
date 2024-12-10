---
title: Test data
type: docs
sidebar:
  open: true
---

###### Create a PDF file containing random data and the size you require
You can define the size of the file in `count` parameter. The below example is for 30 megabytes file.
``` bash
dd if=/dev/urandom of=myfile.pdf bs=1M count=30
```

