# Back Alley Bones — AI / Build Log

## Submission links

- Public game: https://cartercarterwilk-cmd.github.io/back-alley-bones/
- Public source: https://github.com/cartercarterwilk-cmd/back-alley-bones

## Project goal

Build a small, finished browser game using simplified pass-line craps rules. Two people can share one computer, or one person can play a three-level CPU campaign. Each table ends when one bankroll reaches $0.

## Major prompts and changes

1. **Initial build:** Created the matched-wager, two-dice gameplay loop; $20 starting bankrolls; casino, scary-alley, and frat-house locations; visible bankroll, pot, dice, point, feedback, ending, and restart states.
2. **Opponent update:** Added same-computer 1v1 and an automatic CPU opponent.
3. **Visual update:** Replaced simple location colors with original AI-generated scene art: a bright casino, a shadowy alley with a dumpster, and a lawn party around a wooden dice table. Dark overlays preserve control readability.
4. **Campaign update:** Added Alley ($20 each, $1–$5 bets), Frat House ($100 each, $5–$25 bets), and Casino ($1,000 each, $50–$250 bets). Bankrupting the CPU unlocks the next level.
5. **Deployment update:** Published the source and game through a public GitHub repository and GitHub Pages. A packaging problem found on the first live check was corrected before final verification.
6. **Unfamiliar-user revision:** A new player reported that local 1v1 made it hard to tell whose turn it was. Added required, distinct player-name fields before local play. The chosen names now replace “Player 1” and “Player 2” in bankroll cards, shooter labels, wager/match prompts, roll instructions, roll history, round results, winner feedback, and restart state.

## Coherent playable loop

1. Choose local 1v1 or CPU campaign. Local players enter their names.
2. The named shooter sets a legal wager and the opponent matches it.
3. The shooter rolls two dice and receives immediate rules feedback.
4. Come-out 7 or 11 wins; 2, 3, or 12 loses. Any other total sets the point.
5. Repeat the point to win, or roll 7 first to lose.
6. Money transfers, the named next shooter is shown, and a new sequence begins.
7. The game ends visibly when a bankroll reaches $0, with retry, restart, campaign-advance, or lobby controls.

## Verification

- Verified that local play cannot begin until two non-empty, different names are entered.
- Verified that custom names appear in both bankroll cards and in turn/action feedback.
- Verified that matching a wager changes the visible pot and enables the named shooter’s roll.
- Verified that come-out and point outcomes transfer money and update the shooter.
- Verified that CPU play can start without local player-name entry and that the CPU acts automatically.
- Verified the three campaign bankrolls and wager ranges.
- Verified a successful production build and the updated public GitHub Pages URL.

## Unfamiliar-user test and revision

**Tester:** Unfamiliar player/classmate who had not used the game before.

**Observed friction:** In same-computer 1v1, the tester found it difficult to determine which person was currently up because the interface used only “Player 1” and “Player 2.”

**Revision:** Added two required name inputs before local play and replaced generic player numbers with those names everywhere turn ownership matters. The active bankroll card also retains its stronger “SHOOTER” highlight.

**Verified revision:** After the change, a local game was started with two sample names. Both names appeared in the scoreboard, and the active name appeared in wager, match, and roll instructions as the turn changed. This directly addresses the observed ambiguity. The next unfamiliar-user check should confirm this human-facing improvement during the class demo.

## Human ownership and judgment

- Chose a restrained pass-line ruleset rather than attempting every casino craps bet.
- Kept multiplayer on one device so the public version needs no accounts or live server.
- Chose three clearly different bankroll scales while preserving one learnable core loop.
- Used the unfamiliar-player observation to prioritize turn clarity over adding another feature.
- Required both local and live-page checks before treating the revision as complete.

## Concise demonstration plan

1. Open the public URL and point out the two modes and visible build-log link.
2. Select same-computer play, enter two names, and choose a location.
3. Show that the shooter’s name appears beside the bankroll and in the wager instruction.
4. Match a wager, roll, and explain the visible dice, total, pot, point, and feedback.
5. Return to the lobby and show the three-level CPU campaign.
6. Open the source/build log and explain the unfamiliar-user revision.

## Reflection

The most important lesson was that visible state is not automatically understandable state. The game already highlighted the active side, but unfamiliar players still had to translate “Player 1” into a real person. Asking for names made the same underlying turn system immediately more legible. Keeping the ruleset small also made it possible to finish, test, revise, and explain the entire game coherently.
