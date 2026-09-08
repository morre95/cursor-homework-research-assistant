# Engineering skills

En drop-in-katalog med Cursor-skills för vanligt programmeringsarbete: granskning, design, felsökning, TDD, research, tickets och nystart av repo.

Kopiera mappen `HW-3-skills` in i ett projekts `.cursor/skills/` (eller be agenten använda `install-skills`). Inget installationsskript behövs. Cursor hittar varje undermapp som innehåller en `SKILL.md`.

```text
ditt-repo/
└── .cursor/
    └── skills/
        ├── code-review/
        ├── codebase-design/
        ├── diagnosing-bugs/
        ├── grill-from-sources/
        ├── init-repo/
        ├── install-skills/
        ├── prototype/
        ├── research/
        ├── resolving-merge-conflicts/
        ├── tdd/
        └── to-tickets/
```

Befintliga skills i målet skrivs inte över utan att du godkänner det.

## Skills

| Skill | När den används |
| --- | --- |
| `code-review` | Granska diff mot kodstandard och mot spec/intent |
| `codebase-design` | Designa djupa moduler, sömmar och testbara ytor |
| `diagnosing-bugs` | Disciplinerad loop för svåra buggar och prestandaregressioner |
| `grill-from-sources` | Hård intervju av en plan, förankrad i kod, docs och officiella källor |
| `prototype` | Snabba throwaway-prototyper för logik eller UI |
| `research` | Undersök en fråga mot primärkällor och spara ett citerat memo |
| `resolving-merge-conflicts` | Lös merge/rebase-konflikter hunk för hunk utan att avbryta |
| `tdd` | Röd-grön utveckling i vertikala skivor |
| `to-tickets` | Bryt en plan till tracer-bullet-tickets med blockerare |
| `install-skills` | Kopiera den här katalogen in i ett annat repos `.cursor/skills/` |
| `init-repo` | Starta ett nytt projekt efter frågor om typ och tech stack |

## Användning

Öppna repot i Cursor och nämn skillen, till exempel:

```text
Use the tdd skill to add password reset.
Use code-review since main.
Use grill-from-sources on this checkout design.
Use init-repo to start a new mobile app.
```

Skills som `tdd`, `diagnosing-bugs`, `prototype`, `research`, `code-review` och `resolving-merge-conflicts` kan också plockas upp av agenten när uppgiften matchar. `grill-from-sources`, `to-tickets`, `install-skills` och `init-repo` körs bara när du ber om dem.
