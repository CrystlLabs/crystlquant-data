# CrystlQuant forecast data

Pre-game forecasts from the CQ blind model, each graded against the real result. The CQ blind model is
CrystlQuant's forecasting model that never reads the betting price of the game it forecasts.
[CrystlQuant](https://crystlquant.com) publishes it next to the market's chance for every game and grades both afterwards.

Every row is the forecast CrystlQuant's public record grades for that game: one forecast per game, the
last one published before kickoff. Nothing was added or re-run after the games. You can check any row
against the record on crystlquant.com.

## Files

| File | Rows | Dates | Pick right |
| --- | --- | --- | --- |
| [`data/college_football.csv`](data/college_football.csv) | 1,638 games | 5 Sep - 11 Oct 2026 | 1,232 (75.2%) |
| [`data/football_soccer.csv`](data/football_soccer.csv) | 783 matches | 24 Aug - 3 Nov 2026 | 413 (52.7%) |

Direct download (no sign-in):

```
https://raw.githubusercontent.com/CrystlLabs/crystlquant-data/main/data/college_football.csv
https://raw.githubusercontent.com/CrystlLabs/crystlquant-data/main/data/football_soccer.csv
```

```python
import pandas as pd
cfb = pd.read_csv("https://raw.githubusercontent.com/CrystlLabs/crystlquant-data/main/data/college_football.csv")
```

### college_football.csv

US college football, all divisions the model covers. Games appear 30 days after they are played.

- `date`: the game's date (US Eastern)
- `sport`, `league`: American football, College football
- `home`, `away`: the two teams
- `model_pick`: the team the model gave the higher chance to win
- `model_win_chance`: that chance, in percent
- `winner`: the team that won

### football_soccer.csv

Football (soccer): 35 leagues in 24 countries, plus the UEFA Champions League. Matches appear 7 days
after they are played. A match has three possible results, so a right pick is harder than in a two-way sport.

- `date`: the match date (UTC)
- `sport`: Football (soccer)
- `country`, `league`: where the match was played (the Champions League is listed as Europe)
- `home`, `away`: the two clubs
- `model_pick`: the result the model gave the highest chance: the home club, the away club, or Draw
- `model_chance`: that chance, in percent
- `result`: the club that won, or Draw

## Not in the files

No market prices or betting lines, and nothing the model reads to make a forecast.
Every number here is a forecast of the result, not betting advice.

## Updates

Both files are refreshed monthly. The same files are on Kaggle:
[college football](https://www.kaggle.com/datasets/crystlquant/college-football-win-forecasts-graded),
[football (soccer)](https://www.kaggle.com/datasets/crystlquant/football-soccer-match-forecasts-graded).

## Licence

[CC BY 4.0](LICENSE). Please credit CrystlQuant with a link to https://crystlquant.com.
