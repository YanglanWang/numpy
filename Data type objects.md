A data type object (an instance of numpy.dtype class) describes how the bytes in the fixed-size block of memory corresponding to an array item should be interpreted.

It includes five parts:
- type of data(int, float,...)
- size of data
- Byte order of the data (little-endian or big-endian)
- if data type is structured:
  1. name of fields
  2. type of fields
  3. which part of the memory block each field takes
- if data type is sub-array, shape and date type
