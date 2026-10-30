---
name: orig-design-system
description: Use when designing or building any page, section or component for the Orig website. Builds only from the Orig design system (Clay base plus Orig additions).
---

# Orig design system

The look: warm, friendly, generous, handmade (Clay), made specific to Orig by two category colours and the origin label.
Source of truth: `assets/tokens.css` (values) and `assets/components.css` (components). The storybook (`storybook.html`) shows every token and component. Page designs live in `prototypes/`.

## Hard rules
1. Use tokens only. Never write a colour, font, size, radius, shadow or duration directly in a page, and no inline `style` attributes. If a value is missing, propose adding a token first.
2. Use existing components before inventing new ones. If a page needs something new, say so, propose it as a component, and add it to `components.css` and the storybook once agreed.
3. One `display` or `h1` per page. Sections use `h2`, items inside sections use `h3`.
4. One primary button per view. Button labels start with a verb.
5. One inverse section per page, used for the closing call to action.
6. Every page works on a phone at 390px wide, with no horizontal scroll and touch targets of at least 44px.
7. Text contrast at least 4.5:1. Errors are shown in words, not colour alone.
8. Motion is subtle: elements rise and fade in once with `data-reveal`. Respect reduced motion.
9. No fake testimonials, reviews or numbers. Placeholders stay visibly marked until replaced with real ones.
10. Design decisions are made in Claude chat and recorded in the design system or a prototype. When building (Claude Code), never decide design: if something isn't defined, stop and ask with two or three options.

## Orig rules
11. Terracotta (`color-accent`) is the only action colour. `color-taste` and `color-wear` label and tint their category (tags, tile kickers, tile links, media tints); they are never a button or a primary action.
12. Origtaste always uses the taste colours, Origwear the wear colours. Never swap them or use them for anything else.
13. Every product shows an origin label: product, maker, place, harvest or weaving date, organic certificate. If we can't name who made it, we don't sell it.
14. Placeholders use `media--placeholder` (dashed edge) for photos and [square brackets] for missing facts, until the real thing exists.
15. Copy: the brand is Orig, the categories are Origtaste (spices) and Origwear (textiles). Only these two categories. Say "profits", never "sales" or "revenue".
16. The profit split is always one third to producer communities as clean energy, two thirds back into Orig. Show it with `split-bar`; never show an invented amount.
17. Photography: natural light, real producers and real products, never stock.

## Components (class names)
- Layout: `container`, `section`, `section--surface`, `section--inverse`, `section--tight`, `section--flush-top`, `section-head`, `grid grid--2|grid--3`, `split`, `stack`
- Type: `display`, `h1`, `h2`, `h3`, `lead`, `body`, `small`, `eyebrow`, `measure`, `muted`
- Actions: `btn btn--primary`, `btn btn--secondary`, `btn-row`, `link`
- Blocks: `nav`, `nav__basket`, `hero`, `hero--media` (`hero__grid`, `hero__text`, `hero__media`), `page-hero`, `card`, `card__title`, `card__foot`, `card__icon`, `steps` / `step`, `steps--4`, `steps--labelled`, `step__label`, `price` / `price--featured`, `badge`, `badge-row`, `list`, `quote`, `faq`, `cta`, `footer`
- Orig: `origin-label` (`__head`, `__rows`), `tag tag--taste|tag--wear`, `category-tile category-tile--taste|--wear` (`__kicker`, `__title`, `__text`, `__link`), `chapter`, `chapter--reverse` (`__text`, `__media`), `media media--portrait|--landscape|--wide|--tall`, `media--inset`, `media--placeholder`, `media-pair`, `split-bar` (`__return`, `__grow`), `legend` (`legend__dot--return|--grow`)
- Forms: `form`, `form__row`, `field`, `label`, `input`, `field__error`

## Page patterns
- Home (`prototypes/home.html`): nav with basket, hero with media and origin label, two category tiles, then four story chapters: 01 where it starts (producers), 02 straight to you (four labelled steps), 03 back home (profit split), 04 then you visit (Respect Points), closing CTA (inverse), footer with Impressum and Privacy.
- Pricing: page hero, plans (3 price cards, one featured), FAQ, closing CTA
- About: page hero, beliefs (split), closing CTA
- Contact: page hero, form + what happens next (split)

## Before you deliver
- [ ] Only tokens and existing components used, no inline styles
- [ ] Phone, tablet and desktop checked; no horizontal scroll
- [ ] One h1, one primary button per view, one inverse section
- [ ] Category colours only on their own category, never on buttons
- [ ] Contrast and form errors checked
- [ ] Placeholders replaced or clearly marked

## Keeping this skill current
When a decision changes the system (a new token, a new component, a new rule), update this file in the same change. Claude chat should suggest it: "This should go into the design skill."
