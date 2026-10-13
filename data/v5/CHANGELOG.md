# Semantic Domains v5 — Draft Changelog

Summarizes `history/*.yaml` (the original migration pass, frozen) and `changes.yaml` (everything since), and is kept
up to date by hand when either changes. 1802 domains total (10 added). 3 migration hints.

## gaps.yaml

- ADD 1.7.2 "Pollution, environmental damage" — v4 has no domain for pollution, waste, recycling, or climate — all flagged as unowned by the gap audit.
- ADD 4.6.8 "Elections, voting" — 'vote'/'election' flagged as unowned; civic participation vocabulary was missing. *(Removed 2026-10-13; see the Merz review below.)*
- ADD 6.9.7 "Aid and development organization" — 'NGO' flagged as unowned; aid/development work is a major part of daily life in target communities.

## neutrality.yaml

- ADD 2.6.2.4 "Sexual orientation" — v4 filed homosexuality as question 18 of "Sexual immorality", between rape and child abuse, glossed "pervert, perverted". Orientation is not a moral category and gets its own neutral domain.
  ↳ migrate: 2.6.2.3 → 2.6.2.4 (Senses about same-sex attraction/relations previously tagged 2.6.2.3 Q18 → re-tag 2.6.2.4.)
- ADD 2.6.2.5 "Sexual violence" — Non-consensual acts are violence, not 'immorality'.
  ↳ migrate: 2.6.2.3 → 2.6.2.5 (Rape (Q17), child sexual abuse (Q19), and marital sexual abuse (Q5) previously tagged 2.6.2.3 → re-tag 2.6.2.5.)
- RENAME 2.6.2.3 "Sexual immorality" → "Sexual relations considered improper"
- REDESCRIBE 2.6.2.3 — Renamed away from the list asserting "immorality"; scope reframed as community-relative and narrowed only by moving violence/orientation into their own new sibling domains (nothing consensual is orphaned).
- EDIT-Q 2.6.2.3 #1 — v4 'What general words refer to sexual immorality?' had the list asserting the judgment.
- EDIT-Q 2.6.2.3 #2
- EDIT-Q 2.6.2.3 #3 — Also fixes the v4 grammar error 'someone who is sexual immoral'.
- REMOVE-Q 2.6.2.3 #19 "What words refer to having sex with a child?"
- REMOVE-Q 2.6.2.3 #18 "What words refer to sex between two people of the same sex?"
- REMOVE-Q 2.6.2.3 #17 "What words refer to forcing a woman to have sex?"
- REMOVE-Q 2.6.2.3 #5 "What words refer to sexual offenses within a marriage?"
- REDESCRIBE 4.3.1.1 — Descriptive reframe; the evaluative vocabulary itself is kept — languages genuinely have it.
- RENAME 4.9.9 "Irreligion" → "Nonreligion"
- REDESCRIBE 4.9.9 — Descriptive/anthropological reframe; religious vocabulary retained.
- EDIT-Q 4.9.9 #1 — Lead with neutral self-descriptions; mark believer-perspective terms as such.
- EDIT-Q 4.9.9 #4 — Reframe 'thinking against God' neutrally; drop 'paganism' as a belief-of-others term.
- EDIT-Q 4.9.9 #6 — Reframe 'acting against God'; drop the othering 'ungodly/godlessness'.
- EDIT-Q 4.9.9 #7
- EDIT-Q 4.9.9 #10 — v4 framed these as 'beliefs that are evil'.
- EDIT-Q 2.5.8 #6 — Remove the slur 'vegetable' and dated 'retardation' as lead terms.
- EDIT-Q 2.5.8 #7 — Remove the slur 'retard'.
  (Slurs should not be lead example words (STYLE-GUIDE); clinical vocabulary retained.)
- EDIT-Q 1 #1 — Neutral example sentence in place of a scripture quotation.
- EDIT-Q 9.1.1.1 #1 — Drop the 'God exists' clause; keep the grammatical illustrations.

## questions.yaml

- EDIT-Q 1.1.3.3 #7 — Convert the non-template 'What is a single drop of rain?' to the standard 'What words refer to…' frame (STYLE-GUIDE §Templates).
- EDIT-Q 2.3.2.3 #17 — Reframe 'What sounds do people make with their mouths…' to a word-eliciting frame; shorten and plainen for translation.
- EDIT-Q 7.2.1.1 #10 — v4 'walking in various manners' is vague; a clearer prompt elicits better.

## technology.yaml

- ADD 3.5.9.2.1 "Mobile phone" — v4 mentioned 'cell phone' only as a stray example word; mobile phones are central to daily life in target communities.
- ADD 3.5.9.7 "Internet" — No internet/web/email/password vocabulary existed anywhere in v4.
- ADD 3.5.9.8 "Social media, online messaging" — Online social communication has no home in v4.
- ADD 6.6.8.2 "Computers, software" — v4 collapsed all computing into the single word 'computer' under 1960s-style 'machines'.
- ADD 6.8.6.2 "Mobile money, digital money" — Mobile-money systems are a primary way money moves in many target communities; absent from v4.
- EDIT-Q 3.5.9.2 #1 — 'cell phone' was the only mobile reference in v4.
  (Modernize telephone vocabulary; mobile detail lives in new 3.5.9.2.1.)
- EDIT-Q 6.6.5.2 #4 — Add digital/phone cameras.
- ADD-Q 6.6.8.1 "What words refer to generating or storing electricity locally?"
  (Off-grid/solar power is common in target communities.)
- ADD-Q 2.5.7.2 "What words refer to preventing disease with an injection or dose?"
  (Vaccination vocabulary absent from the Medicine domain.)

## changes.yaml — v5 review by Sharon and Johannes Merz (2026-10-13)

- ADD 6.6.8.2.1 "Artificial intelligence" — No vocabulary for artificial intelligence existed in v4 or v5; chatbots, voice assistants and machine translation are now in everyday use.
- REMOVE 4.6.8 "Elections, voting" — Duplicated v4 4.6.6.4 "Election", which the gap audit missed. Removed before release, under the policy that v5 numbers become permanent at release.
  ↳ migrate: 4.6.8 → 4.6.6.4 (Senses tagged 4.6.8 in the draft → re-tag 4.6.6.4.)
- RENAME 4.6.6.4 "Election" → "Elections, voting"
- REDESCRIBE 4.6.6.4 — Broadened to take in the questions of the removed 4.6.8; the v4 question is kept, so nothing tagged here is orphaned.
- ADD-Q 4.6.6.4 "What words refer to choosing not to vote?" (abstain)
- ADD-Q 2.6.5 "What words refer to a person whose sense of being male or female differs from their body at birth?"
  (Gender identity, not orientation, so it belongs here rather than in 2.6.2.4.)
- REDESCRIBE 2.6.2.4 — Points gender identity to 2.6.5; the two domains now cross-link.
- RENAME 6.6.8.2 "Computers, software" → "Computers, hardware, software"
- REDESCRIBE 6.6.8.2 — Covers the machines connected to a computer.
- EDIT-Q 6.6.8.2 #2 — Now covers connected machines too; adds hardware, printer, scanner.
- EDIT-Q 3.5.9.7 #6 — Add sign in, sign out.
- EDIT-Q 2.5.7.2 #2 — Replace the US brand name Tylenol with paracetamol and acetaminophen; add ibuprofen. (v5 only; v4 policy does not cover brand-name changes.)
- ADD-Q 3.5.9.2.1 "What words refer to calling someone and hanging up before they answer, as a signal or greeting?"
  (Flash, beep: common practice where airtime is scarce.)
- ADD-Q 6.6.8.1 "What words refer to producing electricity?"
  (Wind power, turbines, renewable and alternative energy.)
