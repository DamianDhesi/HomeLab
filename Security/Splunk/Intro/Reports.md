can expand a field to get quick reports
- top values
- top values by time
- rare values
- events with the field

get geographic location from src_ip field
```
... | iplocation src_ip
```

use iplocation information to plot data on cluster or world map
```
... | geostats count by Country
```

can save results as reports using "Save As"
- good to have a **naming convention** for reports

can schedule reports to run at timed intervals
- nice when used in a dashboard or for when shared with many users
- can have an action performed after report runs (emailing report to desired parties)