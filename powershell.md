# PowerShell

## Usage

### Get File Hash

```powershell
# Synopsis
Get-FileHash -Algorithm ALGORITHM -Path FILE

# Example
Get-FileHash -Algorithm MD5 -Path GMDX_v9.0.3.exe
```

Supported algorithms

* `SHA1`
* `SHA256`
* `SHA384`
* `SHA512`
* `MD5`
