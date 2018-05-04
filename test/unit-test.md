# Unit Test

## When the Coverage seems fucked up

### Remove SourceMaps

The option `--sourcemaps=false` or `-sm=false` can help the debug when an error occur.  
Nevertheless it can be responsible for weird coverage report (which make it innacurate).

Remove this option from the `ng test` command.

## Error: 1 timer(s) still in the queue.

To fix it, you must use the fakeAsync syntax with a tick and wait for stable fixture.

Example:

```
it('should do ...', fakeAsync(() => {

  // Do some stuff here
    
  tick(500);
  fixture.whenStable().then(() => {
  
    // Add your expectation here
      
  });
}));
```