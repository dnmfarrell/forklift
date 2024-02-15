forklift
--------
The POSIX¹ shell concurrent stream processor!

Forklift reads from stdin and distributes each line of input among its worker pool.

    USAGE
    forklift [-w#] command

    EXAMPLES
    $ for d in {1..10};do echo $d;done | ./forklift 'xargs echo'
    1 2 3 4 5 6 7 8 9 10

    # now concurrently with 2 workers
    $ for d in {1..10};do echo $d;done | ./forklift -w2 'xargs echo'
    2 4 6 8 10
    1 3 5 7 9

For more details on the rationale and implementation, see my blog [post](https://blog.dnmfarrell.com/post/parallel-processing-with-bash/).

1. Except it uses non-POSIX `tail` :|

License
-------
Copyright 2023 David Farrell

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
