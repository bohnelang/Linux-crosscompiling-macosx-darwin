# Linux gcc crosscompiling for Apple Darwin Mac 


A complete crosscompiling environment for compiling simple gcc programs that can be executed  on MacOSX. You compile on Linux and can execute this binary on MacOSX.  



## Acknowledgment
1.  https://github.com/zamaudio/cross-apple This is an *almost* complete cross compiling Apple toolchain for Debian x86_64 in binary form.  It supports ppc, i386 and x86_64 apple targets. (Contains a bug in build-manifest - Version 0 is not allowed.)
1.  http://ppa.launchpad.net/flosoft/cross-apple/ Crosscompiler  apple-x86-gcc  as well apple-uni-sdk-10.6  from flosoft
1.  https://github.com/zamaudio/cross-apple/blob/master/install-cross-apple Howto
1.  https://github.com/phracker/MacOSX-SDKs MacOSX-SDKs: A collection of those pesky SDK folders

## Downloading, building and installation of the .deb-packagues
```
#!/bin/bash

set -e

# Set manualiy - test uname -m if you are not shure: x64_64 = amd64 and i686 = i383
#arch=i386
arch=amd64

echo "Select $arch as arcitecture"


[...]

echo "Success!"
```

## Testing
###  hello.c
```
#include<stdio.h>

int main() {
        printf("Hello World\n");
        return 0;
}

```

### Compile example
- Go to example
- Compile hello-Word example simple:  i686-apple-darwin10-gcc -m64 -std=gnu99  hello.c -o hello_x86-64.app -F/usr/lib/apple/SDKs/MacOSX$FRAMEWORK.sdk/System/Library/Frameworks\ 
- Move binary to an Apple with MacOSX (Darwin) and call in a Terminal ./hello_x86-64.app
