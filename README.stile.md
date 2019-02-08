Re-write unison watch to wrap fswatch.

Watchdog seems to introduce a delay of several seconds and burn an enormous
amount of CPU.

In comparison, fswatch appears to have almost no overhead, even when configured
with a latency of only 0.1 seconds.

I also tried using Wistia's fork, https://github.com/wistia/unox, which also
replaces Watchdog. However, for me it but it seg faults.

My forked code is mostly just about replacing the 'observer' implementation -
almost everything else in unox.py is unchanged.
