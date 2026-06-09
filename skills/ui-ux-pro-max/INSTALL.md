# ui-ux-pro-max (installed skill)

Design-intelligence skill providing a searchable database of UI styles, color
palettes, font pairings, UX guidelines, and chart types, plus a design-system
generator.

- **Source:** https://github.com/nextlevelbuilder/ui-ux-pro-max-skill (MIT)
- Symlinked `scripts/` and `data/` from upstream were resolved into real files
  so this copy is self-contained.

## Usage

```bash
# Plain search
python3 skills/ui-ux-pro-max/scripts/search.py "barbershop landing"

# Generate a tailored design system for a project
python3 skills/ui-ux-pro-max/scripts/search.py "Barber Haircut barbershop" \
  --design-system -p "Haircut Test"
```
