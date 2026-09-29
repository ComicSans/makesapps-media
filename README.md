# makesapps-media

Central store of the media and store listings of the @makesapps apps, plus the finished, approved short videos of the @makesapps account (Instagram, TikTok), attached as release assets so the scheduler can fetch them by URL.

No code, no drafts. The renderer lives elsewhere.

## Contents

- `apps/<app-slug>/`: one folder per app that is on sale in the App Store.
  - `README.md`: App Store ID, bundle ID, version, version date, list of locales with screenshot counts.
  - `<platform>-<version>/<locale>/store.md`: name, subtitle, promotional text, description, what's new, marketing and support URL. No keywords.
  - `<platform>-<version>/<locale>/screenshots/<screenshotDisplayType>/<NN>-<fileName>`: App Store screenshots at original size (PNG) by display type (`APP_IPHONE_67`, `APP_IPAD_PRO_3GEN_129`, ...), in store order. If the store file name already starts with its position number (`01-board.png`, `ipad-01-board.png`), it is kept as is, otherwise `<NN>-` is added.
- Releases, one per week (`2026-W40`, ...): the videos as posted, one MP4 per post. Videos are not in the tree.

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

## Screenshots are in Git LFS

All `*.png` files are stored with [Git LFS](https://git-lfs.com) (see `.gitattributes`). A normal clone only fetches small pointer files for them, with full-size files if Git LFS is installed (`git lfs install` once).

Fetch a single file over HTTP:

```
curl -O https://media.githubusercontent.com/media/ComicSans/makesapps-media/main/<path>
# example
curl -O https://media.githubusercontent.com/media/ComicSans/makesapps-media/main/apps/tsugi/ios-2.0/de-DE/screenshots/APP_IPHONE_67/01-board.png
```

Clone without downloading the images, then pull only what is needed:

```
GIT_LFS_SKIP_SMUDGE=1 git clone https://github.com/ComicSans/makesapps-media.git
cd makesapps-media
git lfs pull --include "apps/tsugi/ios-2.0/de-DE/**"
git lfs pull --include "apps/*/*/en-US/**,apps/*/*/de-DE/**"
```

The old T-023 screenshots (`screenshots/<app>/<en|de>/...`) exist only in the commit `b72dc4a` and earlier, as normal Git objects.
