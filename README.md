# Spinning App

A browser-based spinning session timer with a countdown, activity instructions, a visual RPM metronome, and an FTP (%) workout chart.

**[Open Spinning App](https://perberg70.github.io/Spinning-App/)**

## Quick start

1. Open the app using the link above.
2. Select your workout spreadsheet using **Excel file** in the upper menu bar.
3. Check that the first activity and workout bars appear.
4. Choose a **Delay** before starting: None, 3, 5, or 10 seconds. The default is 5 seconds.
5. Click **Start**.
6. Press **C** to hide the upper menu bar and focus on your workout.

**Press C again to restore the menu, or click the gear icon (⚙) in the upper-right corner.** Hiding the menu does not pause the workout.

## Prepare a workout file

The app accepts `.xlsx`, `.xls`, and `.csv` files. For Excel workbooks, it reads the **first worksheet**. Put column headings in the first row and one workout segment in each following row.

Use these headings:

| Column | What to enter | Example |
| --- | --- | --- |
| Time | Segment duration in seconds; must be greater than zero. | 60 |
| Activity | Instructions displayed during the segment. | Seated climb |
| RPM | Target pedalling cadence for the visual metronome. | 80 |
| Intensity | FTP percentage as an ordinary number, without a percent sign. | 105 |
| Background | Optional image or video URL for the segment. Leave blank for a plain background. | https://example.com/mountains.mp4 |

Only **Time** is required to keep a row. Include Activity, RPM, and Intensity for a useful workout display. Rows without a positive numeric Time are skipped.

### Example workout

| Time | Activity | RPM | Intensity | Background |
| --- | --- | --- | --- | --- |
| 120 | Warm-up | 80 | 50 | |
| 60 | Steady ride | 90 | 80 | |
| 45 | Seated climb | 70 | 105 | |
| 30 | Sprint | 110 | 125 | |
| 120 | Cool down | 75 | 50 | |

Enter an FTP target of 105% as **105**, not `1.05` or an Excel percentage-formatted value. The chart reads the **Intensity** column; a column named FTP is not currently recognised.

## During the workout

- **Start:** begins the workout or resumes it after a pause.
- **Pause:** pauses the countdown and visual metronome.
- **Reset:** returns to the first segment.
- **Pie chart and timer:** show the remaining time in the current segment.
- **Activity text:** shows the current instructions and the next activity.
- **RPM metronome:** provides a visual cadence cue. It does not produce an audible beat.
- **FTP (%) chart:** shows workout intensity on a linear 0–140 scale, labelled every 20 points. Bar widths reflect segment duration. The active bar is highlighted and its fill decreases as the segment progresses. Values above 140 are capped visually at the top.
- **Open Player:** opens FitnessPlayer in another tab. Music playback is separate from the workout timer.

The timer advances through the segments automatically.

## Hide or restore the upper menu

Press **C** on your keyboard to toggle the upper menu bar. This works before or during a workout.

When the menu is hidden, a **gear icon (⚙)** appears in the upper-right corner. Click it to show the menu again.

If C does not work, click an empty area of the page first. The shortcut is ignored while a file input or the Delay dropdown has focus. Use C without Ctrl, Alt, or Command.

The app remembers whether you hid the menu in that browser. If you return to the app and the menu is missing, press C or click the gear icon.

## Backgrounds

Backgrounds are optional and can change for each segment. For direct video links, use a browser-accessible URL ending in `.mp4`, `.webm`, `.ogg`, or `.mov`. Direct background videos play muted and loop.

The app also attempts to embed YouTube and Pexels links, but playback depends on the provider's embedding restrictions and browser settings. A file path on your computer is not a public video URL and will not work as a hosted background.

## Troubleshooting

- **Start is disabled:** load a file with at least one positive numeric Time value.
- **Workout bars are missing:** check that the Intensity column contains numbers greater than zero.
- **No RPM movement:** provide a positive number in the RPM column.
- **Menu is missing:** press C or click the gear icon.
- **Background does not play:** try a direct, publicly accessible video URL or leave Background blank.
- **An older design appears:** refresh with Ctrl+F5 on Windows after a website update has deployed.

## Code and updates

The app's HTML, CSS, and JavaScript are in [index.html](index.html). GitHub Pages publishes the app from the repository's main branch.

To update the app, edit index.html and commit the change to main. Allow the Pages deployment to finish, then refresh the website.
