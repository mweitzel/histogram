# histogram

append a column of stars equal to the number in the first column

## installation

throw `histogram` into your `$PATH`

## usage

either supply a filename or a stream

```bash
# with file
$ histogram file-holding-5-10-3-20
# prints ->
5   *****
10  **********
3   ***
20  ********************

# with with stream
$ cat file-holding-5-10-3-20 | histogram
# prints ->
5   *****
10  **********
3   ***
20  ********************
```

works well in streams

```bash
$ echo 'Buffalo buffalo Buffalo buffalo buffalo buffalo Buffalo buffalo' | tr ' ' '\n' | sort | uniq -c | ./histogram
# outputs:
3  Buffalo  ***
5  buffalo  *****
```

```bash
echo 'Bare bear bearing bare bear bear bare bear' | tr ' ' '\n' | sort | uniq -c | ./histogram
# outputs:
1  Bare     *
2  bare     **
4  bear     ****
1  bearing  *
```

## license

MIT
