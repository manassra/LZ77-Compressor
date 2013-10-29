A Python LZ77-Compressor
===============

A simplified implementation of the LZ77 compression algorithm in python.

## Implementation
The compressor follows the implementation of the standard LZ77 compression algorithm. 

## Setup and Dependencies
First, you will need to clone the repository: 
```
  git clone git@github.com:manassra/LZ77-Compressor.git
```

The `LZ77Compressor` uses the [bitarray](https://pypi.python.org/pypi/bitarray/) as the only dependency. 

This dependency can be install by using [pip](https://pypi.python.org/pypi/pip), the python package manager, as follows: 

``` 
  pip install -r requirements.txt 
```


## Usage
```python
  from LZ77 import LZ77Compressor
  
  compressor = LZ77Compressor(window_size=20) # window_size is optional
```
#### Compressing Files
```python 
  input_file_path = '/Users/manassra/...'
  output_file_path = '/Users/manassra/...'
  
  # compress the input file and write it as binary into the output file
  compressor.compress(input_file_path, output_file_path)
  
  # or assign compressed data into a variable 
  compressed_data = compressor.compress(input_file_path)
```

#### Decompressing Files
```python 
  input_file_path = '/Users/manassra/...'
  output_file_path = '/Users/manassra/...'
  
  # decompress the input file and write it as binary into the output file
  compressor.decompress(input_file_path, output_file_path)
  
  # or assign decompressed data into a variable 
  decompressed_data = compressor.compress(input_file_path)
```
