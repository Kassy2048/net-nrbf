This Python 3 library parses [.NET Remoting Binary Format (NRBF)](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-nrbf/75b9fe09-be15-475f-85b8-ae7b7558cfe5) contents and converts them to Python data structures. Not all data types are supported.
NRBF is what the [BinaryFormatter class](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.serialization.formatters.binary.binaryformatter) produces.

A typical example to use it is:
```python
from net_nrbf import File as NrfbFile

with NrfbFile(file_path) as nrfb:
    data = nrfb.convert()
```

The first argument to `File` can be a file path or a file-like object. Use `File.from_bytes()` to convert from `bytes` objects.