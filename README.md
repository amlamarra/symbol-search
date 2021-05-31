# Symbol Search

Have you ever found an imported symbol (e.g. variable or function) and wondered which of the binary's shared libraries it came from?

This can help you figure it out.

### Dependencies

- `readelf`

### Usage

```
./symbol_search.sh BINARY SYMBOL
```

**Example:**
```
andrew ~/E900 $ ./symbol_search.sh root/usr/sbin/httpd nvram_get
/home/andrew/E900/root/firmadyne/libnvram.so
/home/andrew/E900/root/usr/lib/libnvram.so
/home/andrew/E900/root/usr/lib/libshared.so
```

## Future Improvements

- No set `$search_dir` path
- Check the `Ndx` header of the "`readelf -s`" output to filter out libraries that have that symbol as "undefined"