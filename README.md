# JackpotJoker
Project: Jackpot Joker - Bonus Bonanza
This project is a complete, single-file web game called "Jackpot Joker." It's a roguelike deck-builder inspired by slot machines and modern deck-builders like Balatro. The entire game—logic, styling, and structure—is self-contained within one HTML file using vanilla JavaScript, CSS, and HTML, with no external dependencies.
Gameplay & Core Mechanics
The objective is to meet a target score for the current "Blind" (level) before running out of "Draws" (turns).
 * Drawing & Playing: Players spend a Draw to get a hand of 5 symbol cards. They must then select 3 cards to play on the "payline".
 * Scoring: Points are awarded based on matching symbols on the payline, similar to a classic slot machine (e.g., three Cherries, two Bells, etc.).
 * Jokers & Relics: Players can acquire up to 5 "Joker" cards and one "Relic" card. These provide powerful passive effects, score multipliers, or unique abilities that create synergies and define a player's strategy for a run.
 * Reel Building (Deck Building): Instead of a traditional card deck, the game uses three "Reels." After beating a blind, players enter a shop where they can buy new, more valuable symbol cards to permanently add to their reels, increasing their chances of high-scoring hands.
 * Progression & Shop: After beating a blind, players spin a "Wheel of Fortune" for a random prize and then enter a shop to spend money earned during the level on new Jokers or Symbol cards.
 * Bonus Features: The game includes several expansion features:
   * Bonus Game: Landing three "Bonus Chest" symbols triggers a shell game mini-game for a chance at a valuable prize.
   * Free Spins: Special tokens grant free plays that don't consume a Draw.
   * Persistent Unlocks: Player data, high scores, achievements, and cosmetic unlocks (like reel backs) are saved to localStorage, encouraging replayability.
Code Structure
The entire application is architected within a single .html file.
HTML Structure
 * The main UI is contained within <div id="game-container">.
 * The layout is divided into semantic sections: header, game-stats, relic-and-jokers, hand-area, slot-machine, and action-area.
 * Modals are used for different game states (Help, Shop, Game Over, Collections, Bonus Game). They are hidden by default and shown as needed by the JavaScript.
 * A Tooltip element exists to show card details on a long press, improving user experience on mobile devices.
CSS Styling
 * Self-Contained: All styles are located within a single <style> block in the <head>.
 * Modern CSS: Uses CSS Variables (:root) for easy theming (a retro neon aesthetic), Flexbox, and Grid for a responsive, mobile-first layout.
 * Animations: Includes keyframe animations for card flips (is-flipping), glowing buttons (glow), and the cup shuffle mini-game.
 * Accessibility: Includes a .sr-only class for screen-reader text and uses aria attributes for key interactive areas.
JavaScript Logic
The game logic is contained within a single <script> tag at the end of the <body> and is organized as follows:
 * DOM Element Caching: All necessary DOM elements are queried and stored in constants at the start for performance.
 * Game Data Definitions: Core game rules and card data are stored in constant objects:
   * cardPool: Defines all Symbol and Joker cards, including their names, descriptions, and effects (as functions).
   * payoutTable: A lookup table for the score and money awarded for symbol matches.
   * blindDefinitions: An array of objects defining the score requirements and turn limits for each level.
 * Game State Management: A central gameState object holds all current run information, such as score, money, spins left, reels, active jokers, and the player's hand.
 * Core Game Loop: The primary logic is handled by a set of functions:
   * initGame(): Resets the gameState and starts a new run.
   * drawHand(): Manages drawing cards from the combined reels.
   * playHand(): Moves selected cards to the payline and triggers scoring.
   * calculatePayout(): Determines the score based on the played cards and applies active Joker effects.
   * checkEndConditions(): Checks if the player has won the blind or lost the game.
 * Modular Expansions: The code is clearly commented with sections like --- EXPANSION CODE START ---. New features (like achievements, the wheel, or the bonus game) are added by "hooking" into the original game functions. This is done by storing the original function in a variable and then redefining it to include the new logic alongside a call to the original.
 * Persistent Data: localStorage is used to save and load player statistics, achievements, and unlocks between sessions.
