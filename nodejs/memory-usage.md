Memory usage
============

Rarely, working with NodeJS, we may face a nasty error:

```bash
FATAL ERROR: CALL_AND_RETRY_LAST Allocation failed - JavaScript heap out of memory
```

Presumably, your applications hits the v8's heap limit and throws an error.


> Currently, by default v8 has a memory limit of 512mb on 32-bit systems, and 1gb on 64-bit systems. The limit can be raised by setting --max_old_space_size to a maximum of ~1gb (32-bit) and ~1.7gb (64-bit), but it is recommended that you split your single process into several workers if you are hitting memory limits.

http://stackoverflow.com/questions/12779724/limiting-node-jss-memory-usage


So, adding `--max-old-space-size` flag should solve the issue (note, that flag works in the same way if you write it using dash or lo-dash). Example:

```bash
node --max-old-space-size=4096 myAwesomeApp.js
```


## Related

- Increasing NodeJS memory limits: http://prestonparry.com/articles/IncreaseNodeJSMemorySize/
- process.memoryUsage(): https://nodejs.org/dist/latest-v6.x/docs/api/process.html#process_process_memoryusage)
