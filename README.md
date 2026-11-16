# Circuit competition leaderboard

The page at https://leaderboard.taroreh.com shows the competition's final standings. The competition closed Thursday 2026-11-12 at 11:59 PM PST, and the audit on Saturday 2026-11-14 passed every entry it ran.

The page is frozen. `final/standings.json` is `standings.py`'s reading of the board after the close, with every note checked against the archive on the `competition-archive` branch of the reference repository. On each push, a GitHub Action renders that file with `build.py`. It doesn't read the live board. After the close, the board re-tested every entry under new rules, and the re-test rows replaced the competition rows there, so a live reading would no longer show the competition.

```sh
python3 -I test_build.py
python3 -I build.py final/standings.json site/index.html
```

To read the board yourself, run `standings.py`:

```sh
python3 -I standings.py https://ecdsabreak.taroreh.com --close 2026-11-13T07:59:00 --cache status-cache.json --json standings.json
```
