![PyPI](https://img.shields.io/pypi/v/idev-zwpy) ![Python](https://img.shields.io/pypi/pyversions/idev-zwpy)
# **zwpy**
A [**python**](https://www.python.org) script for hiding secret text into public text utilizing zero-width encoding.
<br />
<br />
<br />
<br />
​<br />
# Installation
With `git` [GitHub](https://github.com):
```
git clone https://github.com/irtsa-dev/zwpy.git
```
With `pip` [PyPi](https://pypi.org/project/idev-zwpy/)
```
pip install idev-zwpy
```
<br />
<br />
<br />
<br />
<br />
<br />

# Usage
<br />
<br />

### Within the CMD/Terminal
If installed with **GIT**:
```
python zwpy.py [-h] {encode,decode,find} ...
```
If installed with **PIP**:
```
zwpy [-h] {encode,decode,find} ...
```
<br />

Utilize `-h` or `--help` parameter for additional help.
```
usage: zwpy [-h] {encode,decode,find} ...

positional arguments:
  {encode,decode,find}
    encode              Will encode secret text into public text using zero-width characters.
    decode              Will decode text to find a secret from zero-width characters.
    find                Will print out a boolean telling if zero-width characters are found in the text, flag exists
                        to print out how many characters were found.

options:
  -h, --help            show this help message and exit
```
```
usage: zwpy encode [-h] [-b BASE] [-k KEY] [-o OUTPUT] [-S] text secret

positional arguments:
  text                  Text to be displayed publicly to the reader.
  secret                Text to be encoded into zero-width characters and hidden in the public text.

options:
  -h, --help            show this help message and exit
  -b BASE, --base BASE  Specifies the base the secret is to be encoded in.
  -k KEY, --key KEY     Specifies key to use for xor operation on the secret.
  -o OUTPUT, --output OUTPUT
                        Specifies the output file name, if not provided the output will be printed out.
  -S, --silent          Disabled progress bars.
```
```
usage: zwpy decode [-h] [-b BASE] [-k KEY] [-o OUTPUT] [-S SILENT] text

positional arguments:
  text                  Text that may contain zero-width characters.

options:
  -h, --help            show this help message and exit
  -b BASE, --base BASE  Specifies the base the secret is was encoded in.
  -k KEY, --key KEY     Specifies key to use for xor operation on the secret.
  -o OUTPUT, --output OUTPUT
                        Specifies the output file name, if not provided the output will be printed out.
  -S SILENT, --silent SILENT
                        Disabled progress bars.
```
```
usage: zwpy find [-h] [-c] text

positional arguments:
  text         Text that may contain zero-width characters.

options:
  -h, --help   show this help message and exit
  -c, --count  Will specify to output how many zero-width characters were found.
```
#### Additional Notes: 
- The following are accepted encoding bases: `binary`, `trinary`, `quaternary`
<br />
<br />
<br />
<br />
<br />
<br />

# Examples
```
zwpy encode "hello there!" "test"

- Will encode "test" into zero-width characters and combine it with "hello there!"
```
```
zwpy encode -b trinary "hello there!" "test"

- Will encode "test" into zero-width characters in a base three (trinary) format before combining it with "hello there!"
```
