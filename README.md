A Python LZ77-Compressor
===============

A simplified implementation of the LZ77 compression algorithm in python.

## Implementation
The compressor follows the implementation of the standard LZ77 compression algorithm. Using a <b>lookahead buffer</b> at a certain position, the longest match is found from a fixed size <b>window</b> of data history. If a match is found, the substring is replaced with a <b>pointer</b> (distance) to the start of the match, and the <b>length</b> of the match. 
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
###### Options
`window_size` an optional integer specifying the length of the history window. Default is 20.

#### Compressing Files
```python 
  input_file_path = '/Users/manassra/...'
  output_file_path = '/Users/manassra/...'
  
  # compress the input file and write it as binary into the output file
  compressor.compress(input_file_path, output_file_path)
  
  # or assign compressed data into a variable 
  compressed_data = compressor.compress(input_file_path)
```

###### Options
`verbose` if True, the compression description is printed to standard output. 

Example: if a file has `"hello hello"`, verbose will print the following description: 
`<0, h> <0, e> <0, l> <0, l> <0, o> <0,  > <1, 6, 5>`
#### Decompressing Files
```python 
  input_file_path = '/Users/manassra/...'
  output_file_path = '/Users/manassra/...'
  
  # decompress the input file and write it as binary into the output file
  compressor.decompress(input_file_path, output_file_path)
  
  # or assign decompressed data into a variable 
  decompressed_data = compressor.compress(input_file_path)
```
