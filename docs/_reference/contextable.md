---
layout: documentation
title: Contextable<> (Class) reference
---

Any argument that is `Contextable` can be provided as a function, that will be called with a `Context` object, which proves access to all the methods available for the current `materialization`, `assertion`, or `operation`.

This is useful when you need to use context methods within an argument.

## Example

When defining a materialization via the JS API, the `query()` method takes a `Contextable<string>` argument, and can be called in two ways:

```js
materialize("example_simple")
  .query("select 1 as test");

materialize("example_context")
  .query(context => `select * from ${context.ref("example_simple")}`);
```