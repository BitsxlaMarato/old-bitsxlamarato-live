# bitsxLaMarato Live page

Hi! This is the code of the #bitsxlaMarato hackathon live page. This Live page was based on the [HackUPC Landing page repository](https://github.com/hackupc/frontend).

## Setup

Install the latest version Node.js (at least v12.6.0). [Find how here](https://nodejs.org/en/download/package-manager/).

```sh
sudo npm cache clean -f
sudo npm install -g n
sudo n latest
```

```sh
git clone git@github.com:hackupc/frontend.git
cd frontend
npm install
```

## Develop

Use `npm run watch` to compile and serve the dist directory in real time. Then view the website at [https://localhost:8080](https://localhost:8080)

**Install linters** extensions in your favorite editor. In VS Code install: `HTMLHint`, `TSLint`, `markdownlint`, `StandardJS`, `stylelint` and `npm`. In other editors they may have similar names.
Or use `npm run lint` to run linters manually from the console to check errors.

We use linters to ensure code quality, please fix all the errors.

Because of cahe busting you may have to clean the cache when you reload to see changes. In Chrome you can do `Ctrl` + `F5`.

**TLDR;**

Run this:

```sh
npm run watch
```

View the website at [https://localhost:8080](https://localhost:8080)

## Deploy

### Deploy to localhost

Use `npm run dist` to compile all dist directory.
The files from `/src/` will be compiled to `/dist/`. Notice that the routes change, so when referencing files check where they are in [/dist/](/dist/]).

Use `npm run serve` to just serve `/dist` at [https://localhost:8080](https://localhost:8080).

**TLDR;**

Run this:

```sh
npm run dist
npm run serve
```

View the website at [https://localhost:8080](https://localhost:8080).

## Edit content

### Update schedule

Clients will poll constantly the schedule.json file. To update the schedule just change the file and deploy.  
New versions of the schedule will be loaded only if 'version' is different.

#### Schedule file

- `id` can be whatever you want, but all ids must be different  
- When writing hours, prepend zeroes: Nice: 01:00; Not-so-nice: 1:00.  
- Events should be ordered by starting hour  
- `baseTimeOffset` should be the same output as executing (new Date()).getTimezoneOffset() in a machine with local time. (UTC - localtime in minutes)  
- `dates` are DD/MM/YYYY format  

> If an event doesn't have endHour, then will show only startHour and it will finish at the same time as it starts.  
Useful to specify events that don't have concept of length or that span through more than one day ("Event start", "Event end")

## Live

Features included

- Optional subscription to events - 5 minutes before notifications
- Schedule live reload
- Fancy schedule with time padding
- Normal tabular schedule
- Countdown
- Full-screen mode by pressing `p`

### Config

Some parameters (offsets, timeouts, defaults) can be changed in `config.live.js`. Keep in mind that some values are just constants and should not be changed.  
Style can be customized in params.scss (note that some parameters should match some variables in config.live.js).

Here you can edit the `FAKE_DATE` parameter to test funtionalities.

## License

MIT © Hackers@UPC
