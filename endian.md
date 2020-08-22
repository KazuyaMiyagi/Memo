# Endian tips

```
$ echo -n "1234" | od -t x # Little Endian
0000000          34333231
0000004
```

```
$ echo -n "1234" | xxd -e # Print Little Endian
00000000: 34333231                             1234

$ echo -n "1234" | xxd # Print Big Endian
00000000: 3132 3334                                1234

$ echo -n "1234" | hexdump -ve '1/1 "%.2x"' # Print Big Endian
31323334
```
