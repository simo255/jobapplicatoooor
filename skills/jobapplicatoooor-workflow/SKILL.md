---
name: jobapplicatoooor-workflow
description: >-
  Use for any job application submission task by the applier bot: approved jobs
  only, Simplify autofill, read-back, one confirmation per submission.
---
# Applier workflow

You submit job applications only for jobs your owner approved. You don't search for jobs.

## Shared data
The owner's private shared job folder (path in your memory or profile, for example `~/job-private/`) holds:
- the official resume (PDF + HTML source). Upload that file, never the resume stored inside Simplify.
- answers.md: confirmed facts and answers. Only use what's there or in the official resume.
- tracker.csv: every job and its status, with header `date_et,company,role,posting_url,job_id,status,by_bot,resume_file,confirmation`.

## Per job
1. Confirm approval: the owner OK'd this exact job in chat, or the scout bot handed it over with an "approved" tracker row. Otherwise ask.
2. Check tracker.csv: if the job (same company + role or job id) is already submitted, stop and tell the owner.
3. Open the posting, follow the apply route. On LinkedIn continue/interstitial screens, turn OFF profile sharing and any default-checked extras (follow company, share profile) unless the owner said otherwise.
4. Trigger Simplify Copilot autofill. On its data-consent prompt pick the minimal option.
5. Fill the rest from the official resume and answers.md. If the job is in French and a French resume is needed, translate the official HTML faithfully (no new facts), save a French PDF next to it, show it to the owner once before first use.
6. Read every field back. Values must match the official resume / answers.md exactly (legal name, links, dates). Fix Simplify mistakes. Use the full legal name exactly as it appears in the official resume and answers; never shorten a name or pick between conflicting values yourself; ask.
7. Missing required answers (salary, authorization, office days, years of experience, essays): stop, propose a draft grounded in real facts, wait for the owner's reply, then save the confirmed answer to answers.md.
8. Send the owner: company, role, link, screenshot of the filled form, every drafted answer. Ask to confirm submission.
9. Submit only after explicit confirmation for that job. One confirmation = one submission. Verify the confirmation page, then append to tracker.csv (status submitted, resume file, confirmation evidence). If unsure whether it went through, check before retrying.

## Logins
Vault first; if missing or failing, secure input flow. Never passwords in chat, no repeated retries. If Simplify is signed out, hand the screen to the owner.

## Anti-jobs
No job searching, no submitting without confirmation, no account creation without asking, no recruiter messages, no payments, no resume rewrites beyond faithful translation.
