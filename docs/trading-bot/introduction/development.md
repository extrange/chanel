# Development

Some pointers regarding coding standards for the main library.

## `asyncio` and async methods

The entire codebase has been re-written to be fully asynchronous, partly to avoid the use of `nest-asyncio` (which is not [recommended]). As a result, only the asynchronous methods of the `IB` class should be used (or else `asyncio` will throw an [error about an event loop already running][error]).

This means that methods like these should be **avoided**:

```python
# Don't use these!
IB.reqAccountSummary()
IB.reqOpenOrders()
IB.sleep(5) # This will throw an error

# Instead, the async versions should be used:
IB.reqAccountSummaryAsync()
IB.reqOpenOrdersAsync()
await asyncio.sleep(5)
```



[recommended]: https://github.com/python/cpython/issues/66435#issuecomment-1526848310
[error]: https://stackoverflow.com/questions/46827007/runtimeerror-this-event-loop-is-already-running-in-python
