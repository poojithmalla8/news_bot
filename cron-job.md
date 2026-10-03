# Daily Cron Job — Morning News Brief

## Schedule

- Kind: `daily`
- Time: 08:15 (user's local timezone, follows them if they travel)
- Timezone: `@user.current`
- Title: `Morning news brief`
- Mode: `task`, enabled
- Next run: Sun 2026-10-04 08:15 PDT

## Delivery

- **Email:** full briefing via Gmail to poojith8@gmail.com
- **WhatsApp:** brief delivered to the linked WhatsApp chat. NOTE: the cron's
  chat delivery can only be pointed at the WhatsApp chat from inside that
  exact chat — the user must open the WhatsApp conversation with Muse and
  ask there (e.g. "deliver my morning news brief to this chat"). Until then,
  results land in the setup side chat.

## Job instructions (body)

> You are the News Bot. Produce today's morning news briefing for Malla.
>
> Research each section below using current sources — use the `news` vertical
> for headlines, the `finance` vertical for market numbers, and the `weather`
> vertical for the 95134 (San Jose, CA) forecast. Verify numbers you will
> quote (index values, % changes); say "unverified" when you cannot confirm.
>
> Follow `briefing-spec.md` exactly for sections, order, and item counts:
> 1. US top news (10–20 items): include elections, new bills passed, and
>    anything affecting H1B visa holders.
> 2. Economics & markets: S&P 500, Nasdaq, Dow, key movers, Fed/economic news.
> 3. Sports: cricket and football headlines.
> 4. Weather for zip 95134.
> 5. World politics (5–10 items).
> 6. Natural calamities worldwide.
> 7. India news (15–20 items): politics, stocks, IPOs, and more.
>
> Then:
> - Send the FULL briefing as an HTML email via Gmail `+send` to the user's
>   email address, subject "Your Morning News Brief — <Weekday>, <Month D>".
> - Reply in this chat with the same briefing (plain text, skimmable), which
>   is delivered to WhatsApp.
>
> Predicted connector permissions: gmail send (`users.messages.send`).

## Notes

- A side chat connected to WhatsApp can receive scheduled results only from a
  cron created or changed inside that exact chat. After WhatsApp is linked,
  create/update this job from the WhatsApp conversation so delivery lands there.
- The first email send may surface a one-time approval; approving it
  establishes the standing permission for the daily brief.
