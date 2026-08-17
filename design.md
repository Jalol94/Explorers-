# Ravagers — Design Document
Document will be updates as design decisions are made. Please see Reamde.md for elevator pitch
## Platform & Status
- Target: Mobile (iOS/Android)
- Structure: Leaning roguelike runs with meta-progression — short runs, permanent unlocks carry over between runs (not finalized)
- Engine: TBD (leaning Godot)

## Setup / Premise
The player captains a rocket exploring an uncharted region of space. The ship is attacked by
raiders called **Ravagers**; the player and one crew member escape into a single compartment
and launch, starting the run with almost nothing.

## Exploration
- Players navigate via a visual map, tapping destinations to travel
- The map starts fully undiscovered/dark and reveals as you explore
- Points of interest:
  - **Mining sites** — gather 1 of 3 resource tiers (Basic / medium / Rare)
  - **Combat encounters** — hostile ships, planeside creatures, Ravager patrols
  - **Emergency beacons** — investigate to recover additional ship compartments and/or grow crew size

## Crew & Jobs
Each crew member has a job, with associated perks, HP, and attack
**Jon - Branches - Role**
Commander - - Strong combat cards with team buffs; high risk(see below)
Engineer - Structural/ Electrical/ Nuclear - Repairs & upgrades the ship (Repair table below)
Miner - - Resource gathering; weakest card in the fight
Pilot - - Ship/shuttle travel speed; can fight but low hp and decent attack
Gunner- Will depend on the weapon(TBD) - Combat, specification will depend on the weapon and will be reflected on the card

##Crew allocation rule: A crew member can only do ONE of the following at a time: work the
ship (repairs), mine, or fight. This is the central resource-tension of the game.

##Expedition capacity; Small shuttles cab sent to planets and any location, at the start the shuttle capacity is at 5 people, can be upgraded to 10-12(not finalized).
The main ship can not land on planets, but can be used instead of shuttle in outer space, if the main ship is used then the player can move as many crew as they want.
Leaving the main ship empty will carry a risk and consequence(tbd). Crew cap on the ship 20(tbd)

### The Commander
- A combat card: strong attack, health, and team-wide buffs
- High risk: if the Commander loses a fight, the Commander AND every other card in that fight
  are permanently lost
- **Losing the Commander ends the run**
- Not confirmed yet whether Commander is always the starting escapee or recruitable later

## Ship Systems & Repair
Each ship system/compartment is independently damageable. Repair requires the matching
Engineer specialty and the matching resource tier:

**System - Engineer Required - Resource Tier**
Structure & living compartments - Structural - Basic 
Engine, Weapons, Shields - Electrical - Basic & Medial
Reactor, Propulsion - Nuclear - Basic & Rare 
If you don't have the right Engineer specialty aboard, the specific system cannot be repaired at all, and will be non functional.

##Scientist Branches
Each branch has its own facility, ship upgrade, and combat role
**Branch - Facility - Ship Upgrade - Combat Role** 
Biologist - Med bay & *Greenery*(name might change, compart that can be build later) - Upgrades Med bay and *Greenery* - Healing and toughness buffs; When stationed in the med bay speeds up crew recovery
Chemist - Lab & Engine room - Propulsion; adds elemental dmg types to weapons(fire, acid, cold) - Boost involves adding AoE and boost weapons that have elemental dmg
Physicist - Reactor & lab - Shields, weapons defense of the ship, reactor - Adds shock to all fighters; grants all fighters a shield that absorbs 1 attack of any magnitude and type
Combat bonuses are player activated with cooldown, all branches share same passive buff (shared passive buff tbd)

**Exception:** the original starting main compartment can be repaired by any Engineer,
regardless of branch.

##Pilot
* Combat: low HP, decent attack
* Outside combat: without the pilot on board shuttles can not be sent. Main ship can be used to respond to outer space locations,
  but is much slower. sending a pilot on a crew with a shuttle will significantly cut travel time

## Mining
* Resource tier is how the site rarity/danger: Basic(common/easy enemies), Medial(uncommon/ harder enemies), Rare(scarce/ very hard enemies).
* Setting up the mine: Investigate the planet, then clear any danger/ enemies, then send miners to establish a mining site.
* An established mining site, will mine automatically. miners are stationed and will send resource to the ship using a capsule. Capsule capacity can be upgraded as well as the ships storage capacity
* An established mining site can be raided. The player will receive an advanced warning, with a ticking timer, giving player time to send reinforcements, or choose to ignore the warning.
If raid is not defended in time, or the fight for defending the site was lost, the site, any upgrades and its miners are lost permanently. The site can be re-cleared and re-established, but
all upgrades that were made including capsule size will have to be rebuild again from scratch.
* Mining sites can hold only miners, but can be upgraded to have two gunners to stand defense.
* Miners are added to the deck during the raid combat. Miners defeated in a raid the was successfully defended will be out of commission for some time. 
They can be relocated to the main ship Med bay to speed up the process.

## Combat 
**Structure**
*Turn-based, alternating single card a actions between player and enemy
*Up to 5 cards active on the field, 4 in the front and 1 in the back row (not mandatory to fill all slots)
*Back row cards cannot attack or be attacked directly, but the ability buffs sill can be activated
*To hit back row card, a front row card must defeat the card(s) guarding it; if the opponent does not refill the front slot, the attacker can choose to hit the back row card or another front row card
*A fight is won when all cards on the opposing side are destroyed
*There is an option to flee combat, if done so then any defeated card will be lost as well as the mission

### Card availability
*Which of your cards are available in a fight depends on which crew you brought on that
  mission/expedition
*Exception: if the ship itself is attacked, ALL crew/cards are available (since they're all aboard)

### Enemy composition
- Enemies are generally also a multi-card team
- Possible exception: wild creature encounters on planets might be a single strong
  card instead of a squad (not fully decided)

### Stakes — two levels
*Cards defeated in a victorious fight, become temporarily unusable until healed, recovery can be sped up with Med bay and sped up more by stationing a biologist.
*Losing the battle leads to permanent lose of all the cards that where used in a fight

### Consequences of losing a fight (beyond card losses)
Depends on where the fight takes place:
*Planet or enemy ship: can also cost the mission/objective
*Player's own ship under attack: results in damage to whichever ship system/compartment
  was being attacked (see Ship Systems table above)

## Open Questions / Not Yet Decided
- Exact win/loss state for the overall run (permadeath vs. setback) — likely tied to losing the Commander
- Whether the Commander can be recruited later or is always the starting character
- Deckbuilding rules: deck size limits, how many crew you can bring on an expedition, synergy systems
- Enemy "nest" encounter rules
- Specification on shared scientist buff
