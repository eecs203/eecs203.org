eecs203.org
===========
EECS 203 course web site

The HTML content in `/docs/` is publicly available at [https://eecs203.github.io/eecs203.org/](https://eecs203.github.io/eecs203.org/).


## Contributing
First clone the website through either HTTP or SSH
HTTP:
```console
$ git clone https://github.com/eecs203/eecs203.org.git
$ cd eecs203.org
```

SSH:
```console
$ git clone git@github.com:eecs203/eecs203.org.git
$ cd eecs203.org
```

To update the website, modify the files in `/docs/`, merge to `main` and push to GitHub.

The main html file that will be displayed on the website is /docs/index.html.

To add custom css, add css to /docs/assets/css/customfontpack.css

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

## Custom font icon pack
We use custom icons for things like "Piazza", "Emacs", etc.  The icons are in a custom generated font pack which lives in `assets/fonts`. `assets/css/customfontpack.css` enables the font to work by assigning each glyph to a unique Unicode value. 

The icon pack contains icons for the following IDEs:
* VS Code
* Visual Studio
* Xcode
* Emacs
* Vim
* CLion
* Atom
* IntelliJ

How to add a new icon:

0. Clone this repository.
1. Obtain a SVG graphic of your desired icon. It **must** be a single color. Make sure your SVG filename is short and clear. For example, the SVG file for "VS Code" is called "vscode". If the filename must have spaces, delimit them with a hyphen (-)
2. Navigate to [icomoon.io/app/](https://icomoon.io/app/#/select).
3. Select the purple "Import Icons" button near the top left.
4. Select `docs/assets/fonts/custom.json` from the website repository in your file explorer.
5. Select the hamburger icon on the right parallel to the title of the icon set then select "Import to Set"
6. Once your icon is in the set, select "Generate Font" near the bottom right.
7. Select "Preferences" near the top.
8. Expand "CSS Selector" and make sure "Use i (for selecting `<i>`) is selected. Make sure the Font Name is "custom" and the Class Prefix is "icon-". Close preferences.
9. Select the download button near the bottom right. Download and unzip `custom-v1.0.zip` into a folder **not** in the repository.
10. Navigate to `custom-v1.0/fonts` and copy the following files
    * `custom.eot`
    * `custom.svg`
    * `custom.ttf`
    * `custom.woff`

    into `docs/assets/fonts` to replace the old files.
11. Navigate to `docs/assets/css/customfontpack.css` and add a selector for your new icon in the format `.icon<icon-name>:before`. In the body add `content: "\<Unicode value>";`. The Unicode value for an icon can be found on the Generate page on icomoon.io under the name of the icon.
12. Add an icon to the website with the following HTML: `<span data-tooltip="<Icon title>"><i class="icon-<icon-name>"></i></span>`
13. Lastly, download the JSON file for your new icon pack from icomoon.io by selecting "Download JSON" on the icon menu where you previously selected "Import to Set" and replace the old `custom.json` file in the repository.
