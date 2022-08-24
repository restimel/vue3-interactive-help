# Debug management

[Back to main page](./main.md)

The debug options are useful for debugging to understand why it doesn't work
as expected.

When the debug option is enabled (with `true` or by enabling only some trace),
it prompts in console a log related to the debug trace.
An error is also emitted like any other [errors](./errors.md), the code value
is between 0 and 99.

## Error code (0xx)

### Related to the component (0 → 9)

| Code | Message | Details | What does it means? |
|:----:|---------|---------|---------------------|
|0 | Tutorial mounted | - **options**: the computed options at tutorial level<br> - **open**: the `open` prop<br> - **tutorial**: the tutorial given in prop | The lib component is mounted |
|1 | Tutorial unmounted | - **options**: the computed options at tutorial level<br> - **open**: the `open` prop<br> - **tutorial**: the tutorial given in prop | The lib component has been unmounted |
|2 | Tutorial started | - **options**: the computed options at tutorial level<br> - **currentIndex**: the current step index | A tutorial has been started |
|3 | Tutorial stopped | - **options**: the computed options at tutorial level<br> - **currentIndex**: the current step index | A tutorial has been stopped |

### Related to steps (20 → 29)

| Code | Message | Details | What does it means? |
|:----:|---------|---------|---------------------|
|20 | Step mounted | - **options**: the computed options at step level<br> - **step**: the description of the `step` object<br> - **tutorialInformation**: some global information about the tutorial | The step component is mounted |
|21 | Step unmounted | - **options**: the computed options at step level<br> - **step**: the description of the `step` object<br> - **tutorialInformation**: some global information about the tutorial | The step component has been unmounted |
|22 | Step changed | - **options**: the computed options at step level<br> - **step**: the description of the `step` object<br> - **tutorialInformation**: some global information about the tutorial | The step has been changed |
|25 | Target elements change | - **options**: the computed options at step level<br> - **tutorialInformation**: some global information about the tutorial<br> - **elements**: list of the targeted elements<br> - **elementsBox**: coordinates in the window of these elements | The targets elements have been changed (either new elements or their position) |