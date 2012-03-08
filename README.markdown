# A Fast CSV Reader
By [Sebastien Lorion](http://sebastienlorion.com)

#Preface
This is a fork of [Sebastien Lorion](http://sebastienlorion.com) original ["A-Fast CSV Reader"](http://www.codeproject.com/Articles/9258/A-Fast-CSV-Reader) article on codeproject.

[Sjoerd Langkemper](https://github.com/Sjord) already put this code on to Github and extended it, adding an extra wrapper and more tests.  

Also consider looking at [NLight](http://nlight.codeplex.com/) - in particular NLight.IO - a more recent CSV parser by [Sebastien Lorion](http://sebastienlorion.com).
#Introduction From CodeProject
_From [Original article](http://www.codeproject.com/Articles/9258/A-Fast-CSV-Reader#Introduction)_

One would imagine that parsing CSV files is a straightforward and boring task. I was thinking that too, until I had to parse several CSV files of a couple GB each. After trying to use the OLEDB JET driver and various Regular Expressions, I still ran into serious performance problems. At this point, I decided I would try the custom class option. I scoured the net for existing code, but finding a correct, fast, and efficient CSV parser and reader is not so simple, whatever platform/language you fancy.

I say correct in the sense that many implementations merely use some splitting method like String.Split(). This will, obviously, not handle field values with commas. Better implementations may care about escaped quotes, trimming spaces before and after fields, etc., but none I found were doing it all, and more importantly, in a fast and efficient manner.

And, this led to the CSV reader class I present in this article. Its design is based on the System.IO.StreamReader class, and so is a non-cached, forward-only reader (similar to what is sometimes called a fire-hose cursor).

Benchmarking it against both OLEDB and regex methods, it performs about 15 times faster, and yet its memory usage is very low.

To give more down-to-earth numbers, with a 45 MB CSV file containing 145 fields and 50,000 records, the reader was processing about 30 MB/sec. So all in all, it took 1.5 seconds! The machine specs were P4 3.0 GHz, 1024 MB.

[Read the rest of the article here](http://www.codeproject.com/Articles/9258/A-Fast-CSV-Reader#latup)

#Licence
Original Copyright (c) 2005-2011 Sébastien Lorion

Copyright (c) 2011 Sjoerd Langkemper

Copyright (c) 2012 Paul Evans and contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

