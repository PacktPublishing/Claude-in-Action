# SOP-003: New client onboarding

**Purpose:** Take a new client from signed engagement letter to a fully set-up file, ready for the client manager to run the first job.
**Owner:** Onboarding Specialist
**Trigger:** A signed engagement letter arrives in the inbox as a completed e-sign envelope, sent directly by the client or forwarded by the managing partner.
**Frequency:** two to four new clients per month, higher in January.
**Tools:** E-sign platform (the authority on signature validity); Google Drive, Engagement Letters folder; practice software (client records, checklists, statuses); Templates folder (welcome email, reminder email); Slack (scope confirmation with client manager); public company register (name/registration lookups when not on the letter).
**Time:** ~40 minutes of active work per client. Elapsed time from letter to "Ready" ranges from two days to three weeks or more depending on how quickly the client returns documents.
**Last updated:** 2026-09-02, incorporated first round of team review feedback (Ella, Tomás, Marcus, Priya); flagged one unresolved sequencing conflict as [OWNER DECISION].
**Last reviewed:** 2026-09-02, confirmed accurate by the onboarding specialist during initial documentation.

## Roles

- **Onboarding Specialist:** verifies the envelope, creates the client record, sends the welcome email, tracks documents, completes the software setup (SOP-004), and hands off to the client manager.
- **Client Manager** (named on the engagement letter, never assumed): confirms scope with the onboarding specialist, owns re-requesting a corrected, re-signed engagement letter when an envelope is rejected, calls clients on overdue documents, sets the first job date and confirms it at handoff.
- **Managing Partner:** resolves job types with no software equivalent (during SOP-004), makes the commercial call on clients who never return documents, and owns the open decisions below.

## Steps

1. Receive the signed engagement letter in the inbox as a completed e-sign envelope, sent directly or forwarded by the managing partner. [TO CONFIRM: exact inbox name, needed for team members without access.]
2. Verify the envelope's signer and signature page (Decision Point 1).
3. Save the letter to the Engagement Letters Drive folder as "[Legal Name], [YYYY-MM-DD]". [TO CONFIRM: exact Drive path. Several folders contain client documents, so new starters need a precise location.]
4. Read the letter for the legal name, services agreed, client type, and VAT registration status.
5. Confirm scope with the client manager on Slack before creating any record (Decision Point 2).
6. Create the client record in the practice software (New Client), entering: legal name, trading name (if any), client type, registration number (companies), tax ID, address, contact name/email/phone, assigned client manager, fee and billing frequency (from the letter), and services in scope, plus VAT number, scheme, and return frequency for VAT-registered companies (Decision Point 3).
7. Send the welcome email with the matching checklist attached (Decision Point 4). [TO CONFIRM: exact Drive path to the Templates folder, and which file is the welcome email template.]
8. Set Document Status to "Awaiting Documents".
9. Track each expected document as a line item on the Documents checklist section of the client record itself (not a separate list), ticking off each with its arrival date.
10. Check each arriving document for legibility and correct type for the entity (Decision Point 5).
11. Escalate per the missing-documents schedule if items remain outstanding (Decision Point 6).
12. Set Document Status to "Ready" once every document has arrived.
13. Complete the software setup by following SOP-004.
14. Post a handoff message on the client record and set Handoff Status to "Handed Off".
15. Ask the client manager to set the first job date, and record their answer on the client record.

> **[OWNER DECISION, steps 6 and 7 sequence]:** Ella states the client record must be created before the welcome email is sent (the order shown above). Marcus sends the welcome email first and creates the record only once the client replies, on the reasoning that a reply confirms genuine engagement and avoids cluttering the system with records for clients who go quiet. The order above follows Ella's account; which is the intended standard needs a decision from the managing partner.

## Decision points

**Decision Point 1 (Step 2), envelope verification**
- **If** the signer's name matches a name on the letter and the final page with both signatures is present: continue at Step 3.
- **If not:** stop. Do not create any record. Return the letter to the client manager in writing, stating what is wrong. Re-requesting a corrected, re-signed letter is their responsibility, not onboarding's. When it arrives, restart at Step 1.

**Decision Point 2 (Step 5), scope confirmation**
- **If** the client manager confirms nothing extra was promised beyond the letter: continue at Step 6, using the services exactly as written in the letter.
- **If** something extra was promised: the client manager either amends the letter or confirms the actual scope in writing. Attach that confirmation to the client record, then continue at Step 6.

*Note: adherence to this step has been inconsistent in practice. It remains required, because it is what keeps the client record's services aligned with what was actually signed.*

**Decision Point 3 (Step 6), VAT registration status (companies only)**
- **If** the company is VAT-registered: capture the VAT number, scheme, and return frequency on the client record. VAT setup (VAT number, scheme, return frequency, first period end, VAT deadlines view, see SOP-004 for exact navigation) runs during SOP-004. The software's suggested first period end is not always correct. If the company registered mid-quarter, set it by hand.
- **If** the company is not VAT-registered, or the client is an individual: skip VAT setup entirely. It does not appear anywhere in SOP-004 for this client.

**Decision Point 4 (Step 7), client type and checklist**
- **If** the client is an individual: attach the Individual checklist.
- **If** the client is a company: attach the Company checklist (incorporation documents, registration number, and, if VAT-registered per Decision Point 3, the VAT registration certificate and last filed return).

**Decision Point 5 (Step 10), document check**
- **If** the document is legible and the correct type for the entity: tick it off on the checklist with its arrival date, and continue at Step 9.
- **If** the document is wrong or incomplete (for example, a personal ID sent for a company engagement): tell the client which document is actually needed, and restart the 5-business-day clock from that correction date.

**Decision Point 6 (Step 11), missing-documents schedule**
- **If** 5 business days pass since the welcome email (or since the last correction) with items still outstanding: send the reminder email from the Templates folder, listing only the missing items.
- **If** 5 more business days pass with no response: escalate to the client manager, who calls the client.
- **If** the client manager's call produces no movement: escalate to the managing partner as a commercial decision.

## Edge cases

- **Symptom:** A file with the intended letter name already exists in the Engagement Letters folder.
  **Response:** The letter was re-signed. Save the new file as "[Legal Name] (resigned), [YYYY-MM-DD]" rather than overwriting.

- **Symptom:** The legal name or registration number isn't clear from the letter.
  **Response:** Check the public register for companies, or the client's ID for individuals. Do not ask the client, looking it up is faster.

- **Symptom:** An individual's tax ID isn't available at intake.
  **Response:** Add it to the checklist as an outstanding item rather than leaving the record field blank.

- **Symptom:** The engagement letter is amended and re-signed after onboarding has already started.
  **Response:** Save the new letter per the naming convention (Step 3), re-read it for scope changes, and flag any material change to the client manager. Leave existing software setup in place; adjust only what the change touches.

- **Symptom:** The letter names a client manager other than the managing partner.
  **Response:** Notify whoever the letter names, not the managing partner by default, since she manages most clients but not all of them.

- **Symptom:** It's January, or another high-volume month.
  **Response:** No procedural change. Expect slower document turnaround and heavier use of the reminder schedule.

- **Symptom:** The handoff message on the client record goes unnoticed, delaying the client manager's awareness that a file is ready (a file was found four days late).
  **Response:** [TO CONFIRM: a single message on the client record is not reliably seen. Needs a decision on a more visible handoff signal, for example a required acknowledgment or a second notification channel.]

- **Symptom:** A client never returns documents even after the managing partner is engaged (Decision Point 6, final step).
  **Response:** [TO CONFIRM: no case has gone past managing-partner escalation so far, so no further response is defined.]

- **Symptom:** Unclear whether setting Document Status to "Ready" triggers anything else automatically in the practice software.
  **Response:** [TO CONFIRM: assumed no effect, but not verified.]

- **Symptom:** Unclear how the practice software derives statutory VAT deadlines from the year end.
  **Response:** [TO CONFIRM: mechanism not currently known. Verify before relying on it in SOP-004.]

- **Symptom:** The onboarding specialist is away.
  **Response:** [OWNER DECISION: no coverage currently exists, so the work waits until they return. Needs a decision from the managing partner.]

- **Symptom:** Nobody else reviews the onboarding specialist's work.
  **Response:** [OWNER DECISION: onboarding is currently self-checked only. Needs a decision on who else reviews it.]

## Done means

The client record exists with all required fields, Document Status is "Ready," software setup is complete per SOP-004, Handoff Status is "Handed Off," and the first job date (set by the client manager) is recorded on the client record.

Checked by: [OWNER DECISION: currently only the onboarding specialist checks their own work, and no second reviewer is defined.]

---

Unresolved items are marked **[TO CONFIRM: ...]**. Open decisions for the managing partner are marked **[OWNER DECISION: ...]** and stay visible until resolved.
