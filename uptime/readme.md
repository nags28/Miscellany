Datadog monitors can track uptime, so if possible, it is better to set up a monitor on the condition you wish to track the uptime of. It's easy to configure monitors to track a wide variety of uptime conditions. One of the disadvantages of this check compared to monitors is that it stores uptime history locally, so you must backup the uptime history log if you use this check. In contrast, monitor uptime history is stored safely by Datadog. At the time that this check was written, it wasn't possible to view a monitor's uptime on a dashboard or via the API, or to view uptime with multiple decimals of precision, but please check if those features are available before using this check! By default this check just measure agent uptime, but you can configure it to measure the uptime of anything by modifying the is_up function.

This check is designed to be as efficient as possible, to make it as generally useful as possible. It stores the current uptime data in a separate file to avoid needing to rewrite the entire uptime log each time the check is run. Older uptime data is appended to the uptime log to avoid rewriting the entire log. The interval at which old uptime data is cleared out is controllable to reduce how often the full log must be rewritten. The uptime log is read each check run, but it will most likely be kept in cache, so the entire uptime log should only be read/written when old uptime data is cleared. The check does not store the uptime log in memory.