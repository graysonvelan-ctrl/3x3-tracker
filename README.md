# 3x3 Box Score & Lineup Tracker

A browser-based tool for tracking individual box score stats and 3-man lineup performance during a 3x3 basketball game, and calculating efficiency metrics from that data.

**Live app:** https://graysonvelan-ctrl.github.io/3x3-tracker/

## What it does

During a game, each player's stats are logged with a tap: made and missed 1-pointers, 2-pointers and free throws, offensive and defensive rebounds, assists and turnovers. The app records which three players are on the court for every event, so each stat counts toward both the individual player and the lineup on the floor at that moment.

The opponent is tracked as a single team total, which is enough to calculate points allowed, defensive rating and rebounding margins without tracking individual opponent players.

From that data it calculates, for every player, every 3-man lineup and the team:

- Shooting: FG%, 2P%, FT%, TS%
- Efficiency: PPP, offensive rating, defensive rating, net rating, plus/minus
- Rebounding: OReb%, DReb%, total rebound share
- Ball handling: Ast%, TO%, Ast:TO ratio
- Offensive and defensive possessions played

The results are shown as tables and can be exported to CSV, either as one combined file or as separate team, player and lineup files.

## How it works

The user enters the roster, stars the three starters and names the opponent. During the game:

- Each player has a row of buttons for their stats. Buttons are only active for players currently on the court.
- Tapping a player's star moves them on or off the court, which is how substitutions are recorded.
- "Our Poss" and "Opp Poss" buttons are tapped when each team's offensive possession ends. One team's offensive possession counts as a defensive possession for the other.
- The opponent row uses the same stat buttons, recorded at the team level.

Individual ratings use team points while the player is on the court, so they reflect on/off impact. Individual PPP uses the player's own scoring: points / (FGA + 0.44 × FTA + TO). Lineup and team PPP use tracked possessions.

An undo button reverses the last action, and games are saved in the browser as they are tracked, so closing or refreshing the page does not lose progress.

## Built with

Vanilla HTML, CSS and JavaScript in a single self-contained file. It runs entirely in the browser with no server or dependencies, and works offline.

## Background

Built as a 3x3 extension of a 5v5 lineup plus/minus tracker, adding individual box score stats and lineup-level shooting, rebounding and ball-handling metrics for tournament use.
