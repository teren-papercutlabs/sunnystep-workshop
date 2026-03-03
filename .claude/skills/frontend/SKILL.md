# frontend

Sunnystep design system and frontend execution protocol. Built on **shadcn/ui + Tailwind CSS** with Sunnystep brand tokens applied on top. Provides brand colors, typography, voice guidelines, and UI patterns for building on-brand interfaces. Use for any frontend, UI, or design work regardless of specific wording used.

## Tech Stack

- **Component library:** shadcn/ui (Radix primitives + Tailwind)
- **Styling:** Tailwind CSS with Sunnystep CSS custom properties
- **Icons:** Lucide React (32px grid, 2px stroke to match brand iconography)
- **Font:** Matter SQ (brand font), fallback to Inter or DM Sans from Google Fonts

Override shadcn's default neutral palette with Sunnystep tokens. The design-tokens reference file has copy-paste CSS variables ready to drop into `globals.css`.

## Brand Identity

Sunnystep is a science-led footwear company. Mission: empower people to move freely and happily. Tagline: "Life is Suntastic."

**Brand pillars:** Science | Happiness | Movement
**Brand archetype:** The Hero — empowering, uplifting, forward motion
**Brand attributes:** Energetic, Positive, Visionary

## Voice Pillars

All copy must embody these three traits:

- **Empowering** — action-oriented language, affirm audience strengths, provide guidance
- **Positive** — uplifting tone, highlight benefits, focus on the positive
- **Visionary** — paint a picture of transformation, incorporate stories of change

## Progressive Disclosure Rule

This skill uses reference files to manage context. **NEVER build UI using only information from this file.** Read the appropriate `reference/*.md` file for full design tokens and patterns.

## Job Routing (MANDATORY)

**BEFORE building any frontend, you MUST read the appropriate reference file.**

| User wants to... | Read this file FIRST |
|------------------|----------------------|
| Build UI / choose colors / style components | `reference/design-tokens.md` |
| Write copy / captions / headlines | `reference/verbal-identity.md` |
