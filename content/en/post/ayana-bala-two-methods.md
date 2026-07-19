---
title: "Ayana Bala: Two Ways to Measure the Same Thing (Classical Table vs Modern Trigonometry)"
date: 2026-07-18T12:05:00+05:30
Description: "Ayana Bala measures a planet's strength from its northern or southern course. There are two legitimate ways to compute it — the classical kranti table and modern trigonometry. Here is how each works, why the classical texts use 24 degrees, and how Vinayak Hora and Jagannatha Hora compare on a real chart."
Tags: ["Shadbala", "Ayana Bala", "Kaala Bala", "Declination", "Vedic Astrology"]
Categories: ["Vedic Astrology", "Shadbala"]
DisableComments: false
draft: false
thumbnail: "images/ayana-bala.webp"
thumbnailAside: true
---

## Where Ayana Bala fits in Shadbala

**Shadbala** ("six-fold strength") measures how well-equipped a planet is to
deliver its results. One of the six sources is **Kaala Bala** — strength that
depends on *time* — and tucked inside it is **Ayana Bala**, the strength a
planet draws from its **northern or southern course**.

An [earlier post](/post/natonnata-bala-explained/) covered Natonnata Bala, the
day–night component. This one takes up Ayana Bala, which is interesting for a
different reason: there are **two entirely defensible ways to calculate it**,
and they give slightly different answers.

---

## The idea: north and south of the equator

As the Earth travels around the Sun, its tilted axis makes every planet appear
to drift north and south of the **celestial equator** over the year. That
north–south position has a name: **declination**, or *kranti* in Sanskrit.

The Sun's declination is what gives us seasons. In late June it is about 23½°
north (long days in India), and in late December about 23½° south (short days).
Every other planet does something similar.

Classical astrology holds that planets have a preference:

| Group | Planets | Gains strength when… |
|---|---|---|
| **North-loving** | Sun, Mars, Jupiter, Venus | in **northern** declination |
| **South-loving** | Moon, Saturn | in **southern** declination |
| **Both** | Mercury | either way |

A planet in its favoured direction is rewarded; in the opposite direction it is
penalised. At the two equinox points — where declination is zero — every planet
scores exactly half marks, 30 points. The Sun's result is then **doubled**,
because its declination *is* the engine of the seasons.

Once you know a planet's declination, the score follows a simple rule:

> **Ayana Bala = 30 × (24 ± declination) / 24**
>
> ( **+** if the planet is in its favoured direction, **−** if not )

So everything hinges on one number: **the declination**. And that is exactly
where the two methods part company.

---

## Method 1: The classical *kranti* table

The classical texts were written for people computing by hand, without
trigonometry tables or calculators. So they supply a **lookup table**.

You first reduce the planet's longitude to a *bhuja* — its angular distance
from the nearest equinox point, always between 0° and 90°. Then you read the
declination off this table, interpolating within the 15° blocks:

| Block | Bhuja range | Value of block | Running total | Declination |
|---|---|---|---|---|
| 1 | 0°–15° | 362′ | 362′ | 6°02′ |
| 2 | 15°–30° | 341′ | 703′ | 11°43′ |
| 3 | 30°–45° | 299′ | 1002′ | 16°42′ |
| 4 | 45°–60° | 236′ | 1238′ | 20°38′ |
| 5 | 60°–75° | 150′ | 1388′ | 23°08′ |
| 6 | 75°–90° | 52′ | 1440′ | **24°00′** |

Notice the blocks shrink — 362, 341, 299, 236, 150, 52. That is the table
quietly encoding a sine curve: declination climbs quickly near the equinox and
flattens out near the solstice. It is an elegant piece of engineering, and it
tops out at exactly **24°**.

**Vinayak Hora uses this method.**

## Method 2: Modern trigonometry

The modern approach computes declination directly:

> **sin(declination) = sin(longitude) × sin(obliquity)**

where *obliquity* is the tilt of the Earth's axis. This is not an approximation
— it is the exact relationship, and a computer evaluates it instantly. Today's
obliquity is about **23.44°**, not 24°.

---

## "But the texts say 24° — is that an error?"

This is the most interesting part, and the answer is **no**.

The Earth's tilt is not fixed. It drifts slowly, currently decreasing by about
47 arc-seconds per century. Running that backwards: an obliquity of 24° was
correct roughly **4,000 years ago**.

So the classical figure is not a rounding error or sloppiness. It is an
accurate measurement — of the sky as it stood when those texts were composed.
The tradition preserved the number faithfully; it is the sky that moved.

This is worth sitting with, because it reframes the whole comparison. The
classical table is not "the crude version." It is a careful, self-consistent
system calibrated to its own epoch.

---

## A worked example

Take the same illustrative chart used in the earlier post:

- **Name:** Rakesh Verma *(illustrative)*
- **Born:** 24 October 1972, **2:14 PM**
- **Place:** Delhi

Let us compute the **Sun's** Ayana Bala.

**Step 1 — the Sun's position on the seasonal circle.** It is at 211.04°.

**Step 2 — reduce to bhuja.** Since 211.04° is past 180°, we take
211.04 − 180 = **31.04°**.

**Step 3 — read the table.** 31.04° lands early in block 3 (30°–45°):

> declination = ( 1002′ − (45 − 31.04) × 19.93′ ) ÷ 60 = **12.06°**

**Step 4 — which side?** Longitudes past 180° are **southern** declination. The
Sun is north-loving, so it is in its *unfavoured* direction and gets the minus:

> Ayana Bala = 30 × (24 − 12.06) / 24 = 14.92

**Step 5 — double it, because it is the Sun:**

> **Ayana Bala = 29.84**

Now the same Sun by modern trigonometry: sin(211.04°) × sin(23.44°) gives a
declination of **11.84°** — about **0.2° less** than the table.

Here the modern method has to be consistent with itself: if declination is
measured against today's 23.44° tilt, then the scoring rule must use 23.44° as
its ceiling too, not 24°. So:

> Ayana Bala = 30 × (23.44 − 11.84) / 23.44 = 14.85, doubled = **29.70**

Two respectable methods, a difference of about **0.14 points**. That is the
whole story in miniature.

---

## Comparing two programs

Here is Ayana Bala for the same chart from **Vinayak Hora** and **Jagannatha
Hora**, two widely used programs:

| Planet | Vinayak Hora | Jagannatha Hora | Difference |
|---|---|---|---|
| Sun | 29.84 | 30.23 | 0.39 |
| Moon | 5.32 | 5.45 | 0.13 |
| Mars | 22.37 | 22.60 | 0.23 |
| Mercury | 53.07 | 52.91 | −0.16 |
| Jupiter | 0.27 | 0.23 | −0.04 |
| Venus | 33.92 | 34.16 | 0.24 |
| Saturn | 0.71 | 0.74 | 0.03 |

*(Values rounded to two decimals.)*

A few things stand out.

**The differences are small — under half a point**, on a scale where Ayana Bala
runs from 0 to 60 (0 to 120 for the Sun, which is doubled). In percentage terms
they are around 1%.

**They run in both directions.** Jagannatha Hora is slightly higher for five
planets and slightly lower for two. A genuine formula error — a wrong tilt
value, a reversed north/south rule — would push consistently *one* way. A
two-way scatter of this size points to a difference in numerical refinement,
not a difference in doctrine.

**Both programs sit close to the classical family.** We tested this directly:
recomputing the whole set with pure modern trigonometry moves the values
*further* from Jagannatha Hora's figures, not closer. So Jagannatha Hora is
evidently not simply "the modern method" — it appears to apply its own
refinement within the classical framework. Its exact variant is not documented
publicly, and we make no claim to have identified it.

---

## So which one is right?

Both are defensible, and it would be overreaching to declare a winner.

The honest position is this. **Vinayak Hora implements the classical
prescription as written** — the traditional table, the traditional 24° — and
does so faithfully and transparently. If you want to know *why* your chart shows
a particular number, you can follow every step by hand, exactly as above. That
transparency is deliberate.

A program using exact trigonometry is, strictly speaking, computing declination
more precisely — but "more precise" is not automatically "more correct" here,
because the classical scoring rule was designed around the classical table and
its 24° ceiling. Mixing a modern declination into a formula calibrated for 24°
introduces a small inconsistency of its own. There is a real argument for
keeping the system internally coherent, which is the choice Vinayak Hora makes.

And the practical consequence? **There isn't one.** A third of a point in Ayana
Bala does not move a planet from strong to weak, does not change which planet is
strongest in a chart, and does not alter a single interpretation. Ayana Bala is
one component of Kaala Bala, which is itself one of six sources of Shadbala.

If your two favourite programs disagree here by a few hundredths, nothing is
broken in either of them. You are simply watching a four-thousand-year-old
measurement and a modern one, both doing their job, differing by about 1%.

---

## In one line

**Ayana Bala rewards a planet for being on its preferred side of the celestial
equator.** Getting there requires a planet's declination — and whether you read
that from a classical table calibrated to a 24° tilt, or compute it from today's
23.44°, you will land within about a percent of each other. The tradition, it
turns out, built better tools than it is usually given credit for.
