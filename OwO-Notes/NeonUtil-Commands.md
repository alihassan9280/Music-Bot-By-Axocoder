# 🎮 NeonUtil Commands — Complete Reference (OwO Bot)

> NeonUtil = OwO ke liye simulator + calculator bot. Prefix: `neon` (short: `n`).
> Website: https://neonutil.vercel.app/ | Help: `neon help <command>`
> Rule: `<required>` `[optional]`

---

## 📑 QUICK INDEX — "mujhe ye karna hai → ye command"

| Kaam | Command |
|---|---|
| Kisi pet ki stats dekhni | `nd <pet> <lvl>` |
| 2 pets compare | `nd <pet> vs <pet>` |
| Apne zoo mein role/stat se pet dhoondna | `nz attacker` / `nz 7-8 7-8` |
| Weapon ki detail / quality | `nw <weaponID>` |
| Apni saari weapons list | `nw my` |
| Team banana / edit | `nt create` / `nt a` / `nt s` |
| Team test (kaun jeetega) | `nb <team> vs <team>` |
| Streak estimate karna | `ng` (NeonUtil server mein) |
| Boss ke liye tools | `nboss ...` |

---

## 1️⃣ DEX — pet/animal info (`nd` / `neon dex`)

| Command | Kaam |
|---|---|
| `nd <pet> <lvl>` | Pet ki real stats us level par. `nd lobbot 80` |
| `nd <pet> <lvl> -ir` | + Internal Resistance & eHP (effective HP) |
| `nd <pet> vs <pet>` | Do pets compare |
| `nd <p1> <p2> <p3> -c` | Bahut saare pets compact view mein |
| `nd <hp> <att> <pr> <wp> <mag> <mr>` | Stats se pet search (wildcards `*`, ranges `3-5`) |
| `nd ... -e cp` / `-i cp` | Rank exclude `-e` / include `-i` |
| `nd owner <user>` | Creator se animals dhoondna |

**Stat boost flags:** `-rune`, `-att`, `-mag`, `-hp`, `-wp`, `-pr`, `-mr`
Example: `nd monkey 60 -rune` | `nd spider 50 -att 20 18.5`
**Aliases:** `animal`, `cp`, `d`

**Stat order yaad rakho:** `HP  STR  PR` / `WP  MAG  MR`

---

## 2️⃣ ZOO — apne zoo inspect karna (`nz` / `neon zoo`)

> Pehle `wz` (owo zoo) likho, phir uspe reply/neeche ye commands.

| Command | Kaam |
|---|---|
| `nz` | Zoo ki cowoncy + essence value |
| `nz <zoo1> <zoo2>` | Do zoos compare (message link/ID) |
| `nz attacker` / `supporter` / `tank` | Role ke hisaab se pets |
| `nz s <team>` / `nz similar <team>` | Team jaise similar pets dhoondna |
| `nz f <name>` / `nz find <name>` | Naam se pet (partial match) |
| `nz <stats>` | Stat range se pets. `nz 7-8 7-8` |
| `nz owner <user>` | Creator se filter |

**Alias:** `z` | **Cooldown:** 3s
Website (bade zoo ke liye): https://neonutil.vercel.app/zoo

---

## 3️⃣ WEAPON — weapons & passives (`nw` / `neon weapon`)

| Command | Kaam |
|---|---|
| `nw <name/ID>` | Weapon ya passive ki detail. `nw rstaff`, `nw sac` |
| `nw <weaponID>` | Apni actual weapon ki quality + breakdown. `nw AL2TYM` |
| `nw <ID> vs <ID>` | Do weapons compare |
| `nw bp <IDs>` | Blueprint banana |
| `nw rr <weapon> p/s` | Reroll chances (passive/stat) |
| `nw my` | Apni saari tracked weapons |
| `nw my <filters>` | Filter: `nw my rstaff shield sac` |

**Weapon inv register karna:** `nw inv on/private/public` → phir `owow` khol ke har page click karo.
**Delete:** `nw inv delete <IDs>` (ya rank C-F, ya "all")
**Aliases:** `w`, `weapons`, `passive` | **Cooldown:** 2s

---

## 4️⃣ TEAM — team banana/edit (`nt` / `neon team`)

| Command | Kaam |
|---|---|
| `nt` / `nt <number>` | Apni team(s) dekhna |
| `nt create <name> -alias <alias> -from <team>` | Nayi team |
| `nt a <pos> <lvl> <pet> <weapon>` | Animal add. `nt a 1 50 hnsowo sstaff wgen` |
| `nt remove <pos>` | Slot hatana |
| `nt s <pos> <lvl/weapon>` | Slot edit. `nt s 3 crune th` |
| `nt lvl <lvl>` ya `<l1/l2/l3>` | Levels set. `nt lvl 50/60/50` |
| `nt o <...>` / `nt override` | Poori team ek saath define |
| `nt sort` / `nt move` | Positions badalna |
| `nt export` / `nt import <JSON>` | Save/load |
| `nt v` / `nt view` | Saare meta templates |
| `nt v <ID>` | Ek template ki detail. `nt v dg_aoe` |
| `nt v <category>` | all, meta, blitz, popular, rstaff, crune, boss |

**Aliases:** `tm`, `t`

### 🏆 Meta Template IDs (nt v se)
`tshdbr` (Triple Sac Hybrid Double Rstaff), `pstaff` (Pstaff Meta),
`pstaff_rstall` (Pstaff Rstall), `crune_pshield` (Crune Pshield),
`pstall_discharge` (Pstaff Discharge ⭐), `spoon` (Spider Crune),
`wand_crune`, `bow_crune`, `fstaff_crune`, `r1pmag`, `pcl`

---

## 5️⃣ BATTLE — team test karna (`nb` / `neon battle`)

| Command | Kaam |
|---|---|
| `nb <enemy>` | Apni team vs enemy |
| `nb <player> vs <enemy>` | Do teams (blueprints bhi chalte hain) |
| `nb <t1> \| <t2> vs <enemy>` | Multiple teams ek saath |

**Useful flags (end mein lagao):**
- `-m` = 50 battles ek saath | `-mm` = super multi (vote karke unlock)
- `-<level>` = levels override. `-60`, `-45/55`, `-70/`
- `-o` = optimized C++ simulator (fast, bade batches)
- `-q<N>` = saari weapon quality N set karo. `-qp<N>` player, `-qe<N>` enemy
- `-r` reverse order | `-win/tie/loss [turns]` outcome force
- `-t<N>` max turns (default 25)

Examples: `nb rstaff vs fbi -mm -o -70/` | `nb -ex` (example list) | `nb -h` (flags)
**Alias:** `b` | **Cooldown:** 1.5s

---

## 6️⃣ GLOBAL — streak estimate (`ng` / `neon global`)

> Sirf NeonUtil support server mein chalti hai (unless perk ho).
> Real players ke data se average streak batati hai.

| Command | Kaam |
|---|---|
| `ng` | Apni selected team ka avg streak |
| `ng <blueprint>` | Team blueprint se estimate |
| `ng w <include> except <exclude>` | Weapon combos se dataset filter |
| `ng -<id>` (replyg) | Specific losses ke khilaf battle |

**Flags:** `-<level>`, `-m[count]`, `-qp<N>` (player quality)
Example:
```
ng
shnsp sstaff th
pastel pstaff th
giraffbot crune hgen
-85 -qp94 -m
```
**Alias:** `g` | Perks check: `npk`

---

## 7️⃣ BOSS — guild boss tools (`nboss`)

| Command | Kaam |
|---|---|
| `nboss ping ws/crate/bcrate/xp <value>` | Reward threshold par ping |
| `nboss fc <level>` | Boss forecast/calc |
| `nboss mn end` | Boss monitor |
| `nt flag boss` | Team ko boss-mode flag |

---

## 8️⃣ OTHER TOOLS
`ncalc` (calculator), `nxd`, `nset` / `nconfig` (settings), `npk` (perks), `ndonate`

---

## 🔑 WORKFLOW — team optimize karne ka tareeqa
1. `wz` → `nz attacker/tank` se apne best pets dhoondo
2. `nw my` se apni best weapons dhoondo
3. `nt create` se team banao / `nt v <template>` copy karo
4. `nb <team> vs <breaker> -mm -o` se test karo
5. `ng` (support server) se final streak estimate lo
6. Theek lage to OwO mein real set karo: `owo team add`, `owo w`

---
_Source: NeonUtil help (Nayolekekw's notes, 23 Oct 2025 – 29 May 2026) + OwO wiki._
