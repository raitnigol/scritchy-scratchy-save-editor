# Scritchy Scratchy Save Editor

Offline browser-based save editor for Scritchy Scratchy exports.

This tool is built around the game’s actual save flow and removes the need to manually understand Base64 or raw JSON.

## What this editor does

- runs fully in your browser (no uploads);
- decodes exported saves automatically;
- lets you edit values through a clear UI;
- generates a valid import string;
- supports raw JSON editing (advanced mode);
- keeps input and output clearly separated;
- avoids hidden steps like “apply changes”.

## How to use

1. In the game, press Export (copies save to clipboard).
2. Paste the save into the editor.
3. Click **Load save**.
4. Edit values.
5. Click **Generate import string**.
6. Click **Copy import string**.
7. Go back to the game and hold Import for about 3 seconds.

## Save format overview

- Base64-encoded JSON;
- contains global progression plus current run data;
- main gameplay data lives in `layerOne`.

## Top-level structure

- `saveVersion`: string;
- `gameVersion`: string;
- `timestamp`: number;
- `playedTime`: number;
- `layerOne`: object;
- `prestigeCount`: number;
- `prestigeCurrency`: number;
- `currentAct`: number;
- `deathByFinalChanceCount`: number;
- `deathByFinalChance`: boolean;
- `fadeInFromWhite`: boolean;
- `isPrestiging`: boolean;
- `deathCount`: number;
- `loanCount`: number;
- `tokens`: number;
- `totalPrestigeCurrencySpent`: number;
- `activeChallenge`: null or unknown;
- `completedChallenges`: array;
- `diamondsGottenFromTicket`: array;
- `dialoguesPlayed`: string[];
- `achievementsGotten`: string[];
- `achievementsClaimed`: string[];
- `unlockedCosmetics`: string[];
- `boughtCosmetics`: string[];
- `equippedCosmetics`: string[];
- `completedOnboardingSteps`: string[];
- `dlcUnlocked`: string[];
- `boughtPrestigeUpgrades`: object<string, number>.

## `layerOne` structure

- `money`: number;
- `timeSpentInThisPrestige`: number;
- `ticketProgressionDict`: object;
- `upgradeDataDict`: object;
- `tableItems`: array;
- `tableItemSaves`: array;
- `jackpotsGotten`: string[];
- `superJackpotsGotten`: string[];
- `lastUnlockedProgressionGoal`: number;
- `totalMoneyEarnedThisProgressionGoal`: number;
- `claimedCustomTableItems`: string[];
- `firstTicketOpened`: boolean;
- `loans`: array;
- `bankruptcyWarningGiven`: boolean;
- `initializedChallenge`: boolean;
- `initializedPerks`: boolean;
- `machineTier`: number;
- `machineFeedCount`: number;
- `machineProcessingTimeLeft`: number;
- `souls`: number;
- `lastTicketUnlocked`: null;
- `electricFanChargeLeft`: number;
- `fanPaused`: boolean;
- `eggTimerChargeLeft`: number;
- `mundoDead`: boolean;
- `trashCanDead`: boolean;
- `boughtScratchOff`: boolean.

## Ticket progression IDs

Each entry has:

- `id`: string;
- `xp`: number;
- `level`: number.

Known IDs:

- `Loan`;
- `Day Job`;
- `Two Win`;
- `Mini Scratch`;
- `Apple Tree`;
- `Quick Cash`;
- `Lucky Cat`;
- `Final Chance`;
- `Sand Dollars`;
- `Scratch My Back`;
- `Snake Eyes`;
- `The Bomb`;
- `Final Chance_2`;
- `Bank Break`;
- `Xmas Countdown`;
- `Thrift Store`;
- `Berry Picking`;
- `Final Chance_3`;
- `Trick or Treat`;
- `Slot Machine`;
- `To the Moon`;
- `Booster Pack`;
- `Final Chance_4`;
- `Final Chance_Win`;
- `Super_Day Job`;
- `Super_Two Win`;
- `Super_Mini Scratch`;
- `Super_Apple Tree`;
- `Super_Quick Cash`;
- `Super_Lucky Cat`;
- `Super_Sand Dollars`;
- `Super_Scratch My Back`;
- `Super_Snake Eyes`;
- `Super_The Bomb`;
- `Super_Bank Break`;
- `Super_Xmas Countdown`;
- `Super_Thrift Store`;
- `Super_Berry Picking`;
- `Super_Trick or Treat`;
- `Super_Slot Machine`;
- `Super_To the Moon`;
- `Super_Booster Pack`;
- `Super_Final Chance_Win`.

## Upgrade IDs

Each entry has:

- `id`: string;
- `buyCount`: number.

Known IDs:

- `The Machine`;
- `Scratch Luck`;
- `Scratch Size_Base Coin`;
- `Tin Coin`;
- `Scratch Size_Tin Coin`;
- `Aluminum Coin`;
- `Scratch Size_Aluminum Coin`;
- `Copper Coin`;
- `Scratch Size_Copper Coin`;
- `Bronze Coin`;
- `Scratch Size_Bronze Coin`;
- `Iron Coin`;
- `Scratch Size_Iron Coin`;
- `Steel Coin`;
- `Scratch Size_Steel Coin`;
- `Titanium Coin`;
- `Scratch Size_Titanium Coin`;
- `Tungsten Coin`;
- `Scratch Size_Tungsten Coin`;
- `Trash Can`;
- `Scratch Bot`;
- `Scratch Bot Speed`;
- `Scratch Bot Capacity`;
- `Scratch Bot Strength`;
- `Fan`;
- `Fan Speed`;
- `Fan Battery`;
- `Sticky Mat`;
- `Badge Collection`;
- `Mundo`;
- `Mundo Speed`;
- `Spell Book`;
- `Spell Charge Speed`;
- `Subscription Bot`;
- `Buying Speed`;
- `Egg Timer`;
- `Timer Capacity`;
- `Timer Charge`;
- `Warp Speed`.

## Prestige upgrade IDs

- `Muscle Memory`;
- `Night Market`;
- `Allowance`;
- `Super Lucky`;
- `Starter Kit`;
- `Tool Belt`;
- `Jackpot Power`;
- `Booster Kit`;
- `Electric Fan`;
- `Completionist`;
- `Self Made Millionaire`;
- `Big Winner`;
- `Pet Lover`;
- `Picky Eater`;
- `Air Condition`;
- `Less is More`;
- `Recycling`;
- `Smart Investment`;
- `Time Travel`;
- `Fully Automated`;
- `Dishwasher`;
- `Fine Dining`;
- `PlateMaster5000`;
- `Experienced`;
- `Clean Freak`;
- `Shopping Spree`;
- `Magic`.

## Dialogue IDs

- `moneyTrouble`;
- `bankrupt`;
- `firstLoan`;
- `trashCanTutorial`;
- `dayJob`;
- `upgrades`;
- `newTicket`;
- `scratchBot`;
- `appleTreeWorms`;
- `fanUnlock`;
- `stickyMat`;
- `death1`;
- `prestigeUnlock`;
- `notBankrupt`;
- `badgeCollection`;
- `mundo`;
- `death2`;
- `catalogue3`;
- `spellBook`;
- `subscriptionBot`;
- `death3`;
- `catalogue4`;
- `eggTimer`;
- `death4`;
- `theMachine`.

## Achievement IDs

- `Take Loan`;
- `Death_1`;
- `Super Jackpot`;
- `Trash Jackpot`;
- `Death_2`;
- `Lucky ticket`;
- `Clicker minigame`;
- `Spend all the worlds money`;
- `Lucky cat`;
- `Wizard`;
- `Visit the Night Market`;
- `Bad kitty`;
- `Death_3`;
- `Time machine`;
- `Death_4`;
- `Idle game`;
- `Win your job`;
- `Soul Siphon`;
- `Winning streak`;
- `Big win`.

## Cosmetics

- `Astronomy_Table`;
- `Pink_Trash Can`.

## Claimed custom table items

- `Upgrade Catalog`;
- `Act 1 Catalog`;
- `Act 2 Catalog`;
- `Act 3 Catalog`;
- `Act 4 Catalog`.

## Onboarding steps

- `ScratchTicket`.

## Table item saves structure

Each entry has:

- `id`: string;
- `cachedSymbols`: array;
- `posX`: number;
- `posY`: number;
- `onStickyMat`: boolean;
- `autoScratched`: boolean.

Known IDs in this save:

- `Trick or Treat`;
- `Slot Machine`.

## Known value behavior

From observed data:

- numbers support very large values, including scientific notation;
- some timers can be negative;
- most counters appear to be integers;
- booleans are standard `true` / `false` values;
- arrays are used for flags and unlock lists;
- many fields tolerate empty arrays;
- some fields allow `null`, such as `lastTicketUnlocked`.

## Unknown or not confirmed

From this sample alone, the following are not yet confirmed:

- maximum values for `xp`, `level`, and `buyCount`;
- full global list of tickets, upgrades, and achievements;
- contents of `cachedSymbols`;
- structure of non-empty `loans`;
- structure of non-null `activeChallenge`;
- valid values for `dlcUnlocked`;
- true caps enforced by the game.

## Safety note

Editing saves can:

- break progression;
- softlock the game;
- create invalid imports.

Always keep one untouched export as backup.
