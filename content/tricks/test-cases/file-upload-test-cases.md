

##### 1. File size validation
Verify that file upload is restricting resource consumption. You can create a file with the size you want via command-line.
The below will create a file called `myFile.pdf` which size is 30 megabytes.
``` bash
dd if=/dev/urandom of=myFile.pdf bs=1M count=30
```

##### 2. File extension validation
Verify that file upload is restricting file extensions which can potentialy harm the system.
The below will create a file called `myFile.exe`.
``` bash
dd if=/dev/urandom of=myFile.exe bs=1M count=30
```