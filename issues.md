# Issues identified and fixes

| Finding | Tool / severity | Change made |
|---|---|---|
| Shell execution from filename | Bandit B605 / High | Replaced shell call with `pathlib` file reading. |
| Broad exception silently ignored | Bandit B110 / Low; Pylint | Added explicit missing-reservation handling and a clear return result. |
| Mutable default list | Pylint W0102 | Use `None` and create a fresh list per booking. |
| Unmanaged file handles and implicit encoding | Pylint R1732/W1514 | Use context managers and UTF-8. |
| Invalid or reversed time slots | Manual review | Validate format, bounds, and start/end order before booking. |
| Shared global mutable scheduler state | Pylint W0603 | Encapsulate reservations, equipment, IDs, and conflicts in `Scheduler`. |
| Equipment could be overallocated | Manual review | Validate requested quantities before inventory changes. |
| Formatting and unused code | Flake8 / Pylint | Remove unused values and correct spacing, line length, and naming. |
