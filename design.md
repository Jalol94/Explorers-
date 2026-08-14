# Ravagers — Design Document

*Living document — updated as design decisions are made. See README.md for the elevator pitch.*

## Platform & Status
- Target: Mobile (iOS/Android)
- Structure: Leaning **roguelike runs with meta-progression** — short runs, permanent unlocks carry over between runs (not finalized)
- Engine: TBD (leaning Godot)

## Setup / Premise
The player captains a rocket exploring an uncharted region of space. The ship is attacked by
raiders called **Ravagers**; the player and one crew member escape into a single compartment
and launch, starting the run with almost nothing.

## Exploration
- Players navigate via a **visual map**, tapping destinations to travel
- The map starts fully undiscovered/dark and reveals as you explore
- Points of interest:
  - **Mining sites** — gather 1 of 3 resource tiers (Basic / medium / Rare)
  - **Combat encounters** — hostile ships, planeside creatures, Ravager patrols
  - **Emergency beacons** — investigate to recover additional ship compartments and/or grow crew size

## Crew & Jobs
Each crew member has a job, with associated perks, HP, and attack stat. Jobs:

Job | Branches | Role 

| Commander | — | Strong combat card w/ team buffs; high risk (see below) |
| Engineer | Structural / Electrical / Nuclear | Repairs & upgrades ship systems (see Repair table) |
| Miner | — | Resource gathering |
| Scientist | Biologist / Chemist / Physicist | TBD |
| Pilot | — | TBD |
| Gunner | Weapon-specific | Combat, specialty reflected on their card |

**Crew allocation rule:** A crew member can only do ONE of the following at a time: work the
ship (repairs), mine, or fight. This is the central resource-tension of the game.

### The Commander
- A combat card: strong attack, health, and team-wide buffs
- High risk: if the Commander loses a fight, the Commander AND every other card in that fight
  are permanently lost
- **Losing the Commander ends the run**
- Not confirmed yet whether Commander is always the starting escapee or recruitable later

## Ship Systems & Repair
Each ship system/compartment is independently damageable. Repair requires the matching
Engineer specialty and the matching resource tier:

| System | Engineer Required | Resource Tier |
| Structure / living compartments | Structural | Basic |
| Engine, Weapons, Shields | Electrical / Nuclear (mixed) | Medial |
| Reactor, Propulsion | Nuclear | Rare |

**Exception:** the original starting main compartment can be repaired by any Engineer,
regardless of branch.

If you don't have the right Engineer specialty aboard, that system cannot be repaired at all
(no partial/slow repair).

## Combat 

### Structure
- Turn-based, alternating single-card actions between player and enemy
- 1–5 of the player's crew cards active on the field at once
- A fight is won when all cards on the opposing side are destroyed
- Cards have abilities beyond basic attack (buffs, heals, etc.), not just stat-vs-stat resolution

### Card availability
- Which of your cards are available in a fight depends on which crew you brought on that
  mission/expedition
- **Exception:** if the ship itself is attacked, ALL crew/cards are available (since they're all aboard)

### Enemy composition
- Enemies are generally also a multi-card team
- Possible exception: wild creature "nest" encounters on planets might be a single strong
  card instead of a squad (not fully decided)

### Stakes — two levels
- **Individual card defeat within a fight:** temporary — the card is down for that battle only,
  returns for the next fight
- **Losing the overall battle:** permanent — every card that fought in that battle is lost for good

### Consequences of losing a fight (beyond card losses)
Depends on where the fight takes place:
- **Planet or enemy ship:** can also cost the mission/objective
- **Player's own ship under attack:** results in damage to whichever ship system/compartment
  was being attacked (see Ship Systems table above)

## Open Questions / Not Yet Decided
- Exact win/loss state for the overall run (permadeath vs. setback) — likely tied to losing the Commander
- Whether the Commander can be recruited later or is always the starting character
- Scientist and Pilot job abilities/roles
- Deckbuilding rules: deck size limits, how many crew you can bring on an expedition, synergy systems
- Mining resource mechanics in detail
- Enemy "nest" encounter rules
