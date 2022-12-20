# daxtracker.
A site that reports my every work-related doing, like an automatic diary. Server-side code may be found at [https://github.com/dakilaledesma/daxtracker.](https://github.com/dakilaledesma/daxtracker.)

## How does it work?
Like any other github.io website, when changes are pushed to the associated repository (such as this one), GitHub Pages will use Jekyll to build the website automatically.

A Python script running on a free GCP instance is responsible for talking to all of the APIs, currently GitHub, Todoist, and Google Sheets, as well as pushing changes to GitHub. Currently, the script is updating a post markdown file (in `_posts`) when any new events are encountered as well as the `_config.yml` file to increment version number. The script is run every 5 minutes through a `cron` job, so there may be a delay of up to 5 minutes. In practice, GitHub-related tasks may have a delay of >2 hours. The main script (pullinfo.py) may be found at [https://github.com/dakilaledesma/daxtracker.](https://github.com/dakilaledesma/daxtracker.), though the quality of the code is quite poor as it was done in haste.

GitHub (through the [Events API](https://github.com/events)) and Todoist tasks are the current platforms being tracked, both combined include the vast majority of work-related tasks I do. Google Sheets is used as an archive of tasks--in case either framework completely dies/loses data. Additionally, it is also used to circumvent API restrictions; for example, GitHub only shows events in the past 90 days. Saving to Sheets allows me to save tasks (and show them on the website) past the 90 day mark.

All events on GitHub associated with me are tracked, other than the ones that include `no-track` in their commit messages (especially commits to this repo that are done automatically by the script). Only tasks in my work-related project on Todoist are tracked.

## Why not host a website yourself?
I've hosted websites before on the same GCP free-tier instances. I found that when doing so, my charges rose to the point where it was definitely not free anymore (might be my fault). I liked this setup instead as it offloads all of the security and networking to much better frameworks than what I'll manage to string together myself. Not to mention that maintenance is very minimal and the cost is free ($0.01/mo).

## Theme
The original theme is [Lanyon](https://github.com/poole/lanyon), though styled to my liking. The site logo/title is styled a lot differently to the original theme, and the sidebar layout was reversed to accomodate the large left-aligned logo. The `messages` class has been heavily changed to more closely mimic the look of GitHub's commit history page. Font families for the site body were changed to be exactly the same as GitHub for the same reason. 

<sup>Below is a description of Lanyon taken from the original `README` file.</sup>

Lanyon is an unassuming [Jekyll](http://jekyllrb.com) theme that places content first by tucking away navigation in a hidden drawer. It's based on [Poole](http://getpoole.com), the Jekyll butler.

![Lanyon](https://f.cloud.github.com/assets/98681/1825266/be03f014-71b0-11e3-9539-876e61530e24.png)
