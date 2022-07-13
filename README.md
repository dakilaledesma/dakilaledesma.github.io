# daxtracker.
A site that reports my every work-related doing, like an automatic diary. Maybe it will be useful by the time I have to enumerate everything that I have done in my Ph.D. dissertation. 

## How does it work?
Like any other github.io website, when changes are pushed to the associated repository (such as this one), GitHub Pages will use Jekyll to build the website automatically.

A Python script running on a free GCP instance is responsible for talking to all of the APIs, currently GitHub, Todoist, and Google Sheets, as well as pushing changes to GitHub. Currently, the script is updating a post markdown file (in `_posts`) when any new events are encountered as well as the `_config.yml` file to increment version number. The Python script and associated resources are not included as they contain API tokens.

GitHub (through the [Events API](https://github.com/events)) and Todoist tasks are the current platforms being tracked, both combined include the vast majority of work-related tasks I do. Google Sheets is used as an archive of tasks--in case either framework completely dies/loses data. Additionally, it is also used to circumvent API restrictions; for example, GitHub only shows events in the past 90 days. Saving to Sheets allows me to save tasks (and show them on the website) past the 90 day mark.

## Theme
### Lanyon

<sup>(desc taken from the original `README`)</sup>

Lanyon is an unassuming [Jekyll](http://jekyllrb.com) theme that places content first by tucking away navigation in a hidden drawer. It's based on [Poole](http://getpoole.com), the Jekyll butler.

![Lanyon](https://f.cloud.github.com/assets/98681/1825266/be03f014-71b0-11e3-9539-876e61530e24.png)
