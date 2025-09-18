# Jackpot Joker

Jackpot Joker is a compact, single-file web roguelike that mashes up slot machines with deck-building. The entire experience lives inside [`Slots.html`](Slots.html) – open it in any modern browser and start spinning.

## How to Play
1. **Draw a hand.** Spend one draw to reveal five symbol cards pulled from your three reels.
2. **Select exactly three cards.** Tap cards to toggle them. The selection chip above your hand tracks how many more you need and glows once you are ready to play.
3. **Play the payline.** Press **Play Selected** to score your chosen trio. Matching symbols award score and coins, and Diamonds double the winning score.
4. **Beat the blind.** Each blind has a score target and a limited number of draws. Reach the goal before you run out to advance.

## Jokers and the Shop
- **Coins** earned from winning hands can be spent in the shop that appears after clearing a blind.
- **Symbol cards** bought in the shop are permanently added to a reel you choose, improving future odds.
- **Joker cards** provide passive bonuses every time you play a hand – from extra draws to bonus money or score boosts.

## Interface Overview
- **Scoreboard** keeps track of your current score, draws left, blind number, and coins.
- **Joker tray** lists every joker you have recruited during the run.
- **Reel summary** shows how many symbols are packed into each reel.
- **Last payline** displays the previous hand and highlights winning cards.
- **Message bar** surfaces helpful reminders, payouts, and joker effect callouts.

## Project Structure
- `Slots.html` contains the HTML markup, CSS styling, and JavaScript game logic.
- There are no external dependencies or build steps – double-click the file or serve it locally to play.

Enjoy the run and chase that jackpot!
