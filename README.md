
# Circular Countdown Timer using HTML, CSS, and JavaScript

## Overview

A customizable circular countdown timer built with HTML, CSS, SVG, and JavaScript. It displays the remaining time inside a circular progress indicator that changes color as the countdown approaches zero.

## Features

- Customizable countdown duration in seconds.
- Circular SVG progress indicator.
- Dynamic time display in `MM:SS` format.
- Color-coded timer states:
  - Green: Normal countdown.
  - Orange: Warning when 10 seconds or less remain.
  - Red: Alert when 5 seconds or less remain.
- Smooth progress animation.
- Responsive, centered layout.

## How It Works

1. **Timer Initialization:** Prompts the user to enter the countdown duration.
2. **Countdown:** Uses `setInterval()` to update the remaining time every second.
3. **Time Formatting:** Converts the remaining seconds into minutes and seconds.
4. **Progress Indicator:** Updates the SVG `stroke-dasharray` to represent the remaining time.
5. **Color Changes:** Updates the progress color according to the warning and alert thresholds.
6. **Timer Completion:** Clears the interval when the countdown reaches zero.

## Implementation

The circular progress indicator uses SVG, while CSS handles its appearance and transitions.

```css
.base-timer__path-remaining {
    stroke-width: 7px;
    stroke-linecap: round;
    transform: rotate(90deg);
    transform-origin: center;
    transition: 1s linear all;
    fill-rule: nonzero;
    stroke: currentColor;
}

.base-timer__path-remaining.green {
    color: rgb(65, 184, 131);
}

.base-timer__path-remaining.orange {
    color: orange;
}

.base-timer__path-remaining.red {
    color: red;
}
```

The JavaScript updates the countdown and calculates the remaining circular progress.

```javascript
function formatTime(time) {
    const minutes = Math.floor(time / 60);
    let seconds = time % 60;

    if (seconds < 10) {
        seconds = `0${seconds}`;
    }

    return `${minutes}:${seconds}`;
}
```

## Customization

- Change `TIME_LIMIT` to set a default countdown duration.
- Modify `WARNING_THRESHOLD` and `ALERT_THRESHOLD` to adjust color-change timing.
- Update the CSS colors to customize the timer appearance.
- Adjust the timer dimensions and font size to suit your layout.

## Use Cases

- Quiz and examination countdowns.
- Workout and interval timers.
- Presentation time limits.
- Game countdowns.
- Session expiration indicators.

## Technologies Used

- HTML5
- CSS3
- SVG
- JavaScript (ES6+)

## Author

**Sangwin Gawande**

Website: [https://sangw.in](https://sangw.in)

---

Cheers!!
