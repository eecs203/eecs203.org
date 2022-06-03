eecs203.org
===========
EECS 203 course web site

The HTML content in `/docs/` is publicly available at [https://eecs203.github.io/eecs203.org/](https://eecs203.github.io/eecs203.org/).

## Contributing
To update the website, modify the files in `/docs/`, merge to `main` and push to GitHub.

Test locally by navigating to http://localhost:8000/
```console
$ cd docs/
$ python3 -m http.server
```

## CSS Library
We use the Fomantic-UI CSS library, which is mobile-friendly.  You'll want to refer to the [Fomantic-UI docs](https://fomantic-ui.com/introduction/getting-started.html) for how to use features like `sidebar` or `cards`.  Fomantic includes a complete [port of FontAwesome icons](https://fomantic-ui.com/elements/icon.html).


## Calendar
The home page uses the FullCalendar JS library to render the official staff Google Calendar. It is configured to recolor events based on their title, and displays a popup with the event's title and location.

Each semester, remember to update the Google Calendar id (`googleCalendarId`) in the JavaScript code at the end of `index.html`.

If you want to change the colors, modify the `recolorCalendarEvent()` function in `index.html`.

If the Google Calendar API key is not working, follow the guide on this page to obtain a new API key: [https://fullcalendar.io/docs/google-calendar](https://fullcalendar.io/docs/google-calendar).
