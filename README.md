# gw2api-scraping

[![Travis](https://img.shields.io/travis/gw2efficiency/gw2api-scraping.svg?style=flat-square)](https://travis-ci.org/gw2efficiency/gw2api-scraping)
[![Coveralls](https://img.shields.io/coveralls/gw2efficiency/gw2api-scraping/master.svg?style=flat-square)](https://coveralls.io/github/gw2efficiency/gw2api-scraping?branch=master)

> Scraping unofficial sites for information the API can't provide.

**:bomb: NOTE: This module is still heavily in development. Please don't use it yet.**

## Install

```
npm install https://github.com/gw2efficiency/gw2api-scraping
```

This module can be used for Node.js as well as browsers using [Browserify](https://github.com/substack/browserify-handbook#how-node_modules-works). If you
run it in browsers, not all methods are available due to [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

(Note: Babel gets pulled in as a dependency, because the module is written in ES7 and 
gets compiled into ES5 during the installation. The Babel code is **not** included in the module, 
don't be shocked at the dependency tree. :wink:)

## Usage

```js
const scraping = require('gw2api-scraping')

// Get the current offers for claim tickets from wiki.guildwars2.com
let offers = await scraping.claimTicketOffers()

// Get the dye categories (materials, sets, colors) from wiki.guildwars2.com
let categories = await scraping.dyeCategories()

// Get the mini set names from wiki.guildwars2.com
let sets = await scraping.miniSets()

// Get the picture for an item from wiki.guildwars2.com
let itemPicture = await scraping.itemPicture('Incinerator')

// Get the current dungeon records from gw2-dungeons.net
let records = await scraping.getDungeonRecords()

// Get the current achievement leaderboard from guildwars2.com
// Note: this takes ~40 seconds because of heavy rate limiting
let leaderboard = await scraping.achievementLeaderboard()
```

## Tests

```
npm test
```

The tests of this module get executed against the live sites instead of mock objects,
because the structure of the scraped pages could change at any time without notice.

## Licence

MIT