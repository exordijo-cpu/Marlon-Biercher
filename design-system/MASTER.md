# Design System — Haircut Test (Barbershop)

> Source of Truth. Vintage / retro, warm, maskulin, premium.
> Kuratiert mit `ui-ux-pro-max` (Stil: *Vintage Analog / Retro Film* · Palette: warm brown + amber + cream · Typo: Abril Fatface / Merriweather).
> Seiten-spezifische Abweichungen liegen in `design-system/pages/<page>.md` und **überschreiben** diese Datei.

---

## 1. Markenhaltung

- **Mood:** klassischer Barbershop — Leder, Messing, Holz, warmes Licht, handwerklich, zeitlos.
- **Keywords:** vintage, retro, warm, maskulin, premium, handwerklich, nostalgisch.
- **Vermeiden:** Neon, SaaS-Blau, kühle Grautöne, billige Verläufe, schnelle/hektische Animationen.

## 2. Stil — Vintage Analog / Retro Film

- Warme, leicht entsättigte Farben (Sepia-Tendenz), feine Film-/Papierkörnung als Textur.
- Materialanmutung: Leder/Holz/Messing statt Glas. Weiche, warme Schatten.
- Effekte sparsam: dezente Körnung (`grain-opacity ~0.08–0.12`), warmer Lichtschein, sanfte Fade-Ins.
- Performance ⚡ gut · Accessibility ✓ WCAG AA (Kontraste unten geprüft).

## 3. Farben (Design Tokens)

Dunkel ist die Default-/Hero-Stimmung (maskulin, premium). Light dient für textlastige Seiten.

### Dark (Default)
| Rolle | Hex | Token |
|------|-----|-------|
| Background | `#1A1410` | `--color-background` |
| Surface / Card | `#241C16` | `--color-card` |
| Muted Surface | `#2E241C` | `--color-muted` |
| Foreground | `#F5E6C8` | `--color-foreground` |
| Muted Foreground | `#C9B79A` | `--color-muted-foreground` |
| Primary (Brass/Brown) | `#B45309` | `--color-primary` |
| On Primary | `#1A1410` | `--color-on-primary` |
| Secondary (Leather) | `#92400E` | `--color-secondary` |
| Accent / CTA (Amber) | `#D97706` | `--color-accent` |
| Barber Red (Akzent) | `#9A3412` | `--color-barber` |
| Border | `rgba(245,230,200,0.12)` | `--color-border` |
| Ring (Focus) | `#D97706` | `--color-ring` |
| Destructive | `#B91C1C` | `--color-destructive` |

### Light (Cream)
| Rolle | Hex | Token |
|------|-----|-------|
| Background | `#FFFBEB` | `--color-background` |
| Surface / Card | `#FFFFFF` | `--color-card` |
| Muted Surface | `#F5EFE2` | `--color-muted` |
| Foreground | `#1A1410` | `--color-foreground` |
| Muted Foreground | `#6B5B45` | `--color-muted-foreground` |
| Primary | `#92400E` | `--color-primary` |
| On Primary | `#FFFFFF` | `--color-on-primary` |
| Accent / CTA | `#B45309` | `--color-accent` |
| Border | `#EADFC8` | `--color-border` |
| Ring (Focus) | `#92400E` | `--color-ring` |

> Kontrast geprüft: Cream `#F5E6C8` auf `#1A1410` ≈ 12:1; `#1A1410` auf Amber `#D97706` ≈ 6:1 (AA für Text & große Glyphen).

## 4. Typografie

- **Headings:** `Abril Fatface` — vintage Display, für Logo/H1/H2 (Salon-Schild-Anmutung).
- **Body:** `Merriweather` (300/400/700) — seriöser, lesbarer Serif.
- **Optional Akzent (Labels/Buttons):** `Oswald`/`Bebas Neue` — condensed, „Barber-Schild"-Look. Sparsam einsetzen.
- **Mood:** retro, nostalgisch, dramatisch, hochwertig.

```css
@import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Merriweather:wght@300;400;700&family=Oswald:wght@500;600&display=swap');
```

**Type Scale:** 12 · 14 · 16 (Body) · 18 · 24 · 32 · 48 · 64 (Hero) — Line-height Body 1.6.

## 5. Spacing & Layout

- 4/8px-Raster. Section-Rhythmus: 16 / 24 / 32 / 48 / 64.
- Container max-width `~1200px` (`max-w-6xl`), großzügige Gutter.
- Breakpoints: 375 / 768 / 1024 / 1440. Mobile-first, kein horizontaler Scroll.

## 6. Komponenten-Leitlinien

- **Buttons:** rechteckig bis leicht gerundet (`radius 4–6px`), Messing-Amber Primary, klarer Hover (Helligkeit/Opacity, 150–300ms), `cursor-pointer`.
- **Cards:** warme Surface, 1px warme Border, weicher Schatten (`0 8px 24px rgba(0,0,0,0.25)` im Dark).
- **Icons:** SVG (Lucide/Heroicons) — **keine Emojis**. Konsistente Strichstärke (1.5–2px). Touch-Target ≥44px.
- **Bilder:** warmer Sepia-Tint, dezente Körnung; `width/height` setzen (kein Layout-Shift).

## 7. Landing-Struktur (Pattern: Storytelling + Feature-Rich)

1. **Hero** — dunkel, großes Abril-Fatface-Logo „Haircut Test", Tagline, Primär-CTA „Termin buchen" über dem Fold.
2. **Services** — Cards (Haarschnitt, Bart, Rasur, Styling) mit Preis.
3. **Story / Über uns** — Handwerk, Tradition (warmes Foto, Körnung).
4. **Galerie / Vorher-Nachher**.
5. **Team / Barber** — Portraits.
6. **Bewertungen** (Social Proof).
7. **CTA + Öffnungszeiten + Standort/Karte**.
8. **Footer** — Kontakt, Social.

## 8. Animation

- 150–300ms Micro-Interactions, ease-out beim Einblenden. Nur `transform`/`opacity`.
- Sanfte Fade/Slide-Ins beim Scrollen, max. 1–2 Elemente pro View. `prefers-reduced-motion` respektieren.

## 9. Pre-Delivery Checklist

- [ ] Keine Emojis als Icons (SVG nutzen)
- [ ] `cursor-pointer` auf allen klickbaren Elementen
- [ ] Hover-States mit 150–300ms Transition
- [ ] Textkontrast ≥4.5:1 (Light **und** Dark separat geprüft)
- [ ] Sichtbare Focus-States (Keyboard-Nav)
- [ ] `prefers-reduced-motion` respektiert
- [ ] Responsive: 375 / 768 / 1024 / 1440px
