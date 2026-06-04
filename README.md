# 🕐 Is My Clock Correct?

A simple webpage that checks whether your computer's clock is accurate. Open it and it immediately tells you if your time is right.

Compares your browser clock against internet time servers, accounts for network latency, and rechecks automatically every 30 seconds. Works in light and dark mode.

## Results

| Result | Meaning |
|---|---|
| ✅ Your clock is correct | Offset under 2 seconds — you're fine |
| ⚠️ Your clock is slightly off | Off by 2–15 seconds — usually harmless, but worth fixing |
| ❌ Your clock is wrong | Off by more than 15 seconds — check your date & time settings |

## How the offset is calculated

The page records the local time before and after the fetch. The midpoint of that window is used as the estimated moment the server stamped the time, which cancels out most of the one-way network delay — the same basic principle NTP uses.

```
offset = local_time_at_midpoint - ntp_time
```

Positive offset = your clock is ahead. Negative = behind.

## License

MIT
