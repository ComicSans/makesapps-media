# makesapps-media

Central store of the media and store listings of the @makesapps apps, plus the finished, approved short videos of the @makesapps account (Instagram, TikTok), attached as release assets so the scheduler can fetch them by URL.

No code, no drafts. The renderer lives elsewhere.

## Contents

- `apps/<app-slug>/`: one folder per app that is on sale in the App Store.
  - `README.md`: App Store ID, bundle ID, version, version date, list of locales with screenshot counts and where they live.
  - `<platform>-<version>/<locale>/store.md`: name, subtitle, promotional text, description, what's new, marketing and support URL. No keywords. All locales are in the tree.
  - `<platform>-<version>/<locale>/screenshots/<screenshotDisplayType>/<NN>-<fileName>`: App Store screenshots at original size (PNG), by display type (`APP_IPHONE_67`, `APP_IPAD_PRO_3GEN_129`, ...), in store order. In the tree for `en-US` and `de-DE` only. If the store file name already starts with its position (`01-board.png`, `ipad-01-board.png`), it is kept as is, otherwise `<NN>-` is added.
- Release `store-2026-09-29` (App Store assets 2026-09-29): the screenshots of all other locales, as uncompressed ZIPs, one per app and device. Details below.
- Weekly releases (`2026-W40`, ...): the videos as posted, one MP4 per post. Videos are not in the tree.

## Source

App Store Connect, the version on sale (`READY_FOR_SALE`, highest version per platform), state 2026-09-29. Not the local `fastlane/` folders of the app repos, which partly hold drafts of upcoming versions.

## Apps

| Slug | App | Store ID | Bundle ID | Version | Locales |
|---|---|---|---|---|---|
| `claudio` | CLAUDIO: Audiobooks & Music | 6760961153 | tobias.reithmeier.iCloud-Audio-Player | iOS 14.1 | 37 |
| `sudoku-pro` | Sudoku Pro: Puzzles & Trainer | 6760598939 | tobias.reithmeier.minisudoku | iOS 4.4 | 50 |
| `find-picture-pairs` | Find Picture Pairs | 6778074294 | tobias.reithmeier.zen-match | iOS 2.1 | 50 |
| `quadrivium` | Quadrivium: Logic Squares | 6799608995 | tobias.reithmeier.logicsquares | iOS 1.0 | 50 |
| `tsugi` | Tsugi: Zen Dominosa Puzzle | 6761734350 | tobias.reithmeier.tsugi | iOS 2.0 | 50 |
| `nonoquest` | NonoQuest | 6769264877 | tobias.reithmeier.PictoQuest | iOS 2.0 | 50 |
| `365-lens` | 365 Lens: Photo Challenge | 6760582791 | tobias.reithmeier.365lens | iOS 1.0.1 | 2 |
| `plot-spark` | Plot Spark | 6760355038 | tobias.reithmeier.storyarchitect | iOS 2.0.1 | 1 |

## Release `store-2026-09-29`

Each ZIP holds the screenshots of every locale except `en-US` and `de-DE` (those are in the tree), with the same path layout as the tree, so unpacking it into the repo root fills in the missing folders: `apps/<slug>/ios-<version>/<locale>/screenshots/<displayType>/...`. Stored without compression, PNG files are the originals from the store. Every file is below 2 GB.

| File | Content | Size |
|---|---|---|
| `claudio-ios-14.1-ipad.zip` | CLAUDIO: Audiobooks & Music, iPad screenshots, 35 locales | 1165 MB |
| `claudio-ios-14.1-iphone.zip` | CLAUDIO: Audiobooks & Music, iPhone screenshots, 35 locales | 796 MB |
| `find-picture-pairs-ios-2.1-ipad.zip` | Find Picture Pairs, iPad screenshots, 48 locales | 438 MB |
| `find-picture-pairs-ios-2.1-iphone.zip` | Find Picture Pairs, iPhone screenshots, 48 locales | 325 MB |
| `nonoquest-ios-2.0-ipad.zip` | NonoQuest, iPad screenshots, 48 locales | 473 MB |
| `nonoquest-ios-2.0-iphone.zip` | NonoQuest, iPhone screenshots, 48 locales | 334 MB |
| `quadrivium-ios-1.0-iphone.zip` | Quadrivium: Logic Squares, iPhone screenshots, 48 locales | 112 MB |
| `sudoku-pro-ios-4.4-ipad.zip` | Sudoku Pro: Puzzles & Trainer, iPad screenshots, 48 locales | 274 MB |
| `sudoku-pro-ios-4.4-iphone.zip` | Sudoku Pro: Puzzles & Trainer, iPhone screenshots, 48 locales | 270 MB |
| `tsugi-ios-2.0-ipad.zip` | Tsugi: Zen Dominosa Puzzle, iPad screenshots, 48 locales | 267 MB |
| `tsugi-ios-2.0-iphone.zip` | Tsugi: Zen Dominosa Puzzle, iPhone screenshots, 48 locales | 196 MB |

`365-lens` and `plot-spark` only have `en-US` and `de-DE` (or `en-US`), so they are completely in the tree.
