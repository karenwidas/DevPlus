# Systems Inventory — DevPlus / CoCard Operations

**Last updated:** 2026-07-13 — added 9 HTML files (merchant form, approve, email templates, EULA, privacy policy, decrypt tool, icon preview); removed quote-builder (deleted); added 3 n8n CRM exports (convert-lead, send-form, merchant-form-submit)
**Maintained by:** Claude Code scheduled agent (weekly, Mondays)

---

## Tools & Plans

| Tool | Plan | Cost | Notes |
|---|---|---|---|
| Airtable | Free | $0 | Data layer for all CoCard operations |
| Claude | Pro | $20/mo | AI assistant; Claude Code CLI for dev work |
| n8n | Starter | $20/mo | Automation / workflow engine; karenwidas.app.n8n.cloud |
| SignWell | Light | $12/mo | E-signature for merchant agreements |
| GitHub | Free | $0 | Repo: karenwidas/DevPlus → karenwidas.github.io/DevPlus (GitHub Pages) |
| Obsidian | Free | $0 | Personal knowledge base / notes |
| Dropbox | Plus | ~$10/mo ($120/yr) | File sync / storage |
| QuickBooks Online | — | ~$40/mo | Accounting |
| DocuSign | Free | $0 | Unused — SignWell preferred |

**Total: ~$102/mo + QBO (~$142/mo combined)**

---

## GitHub Repo — karenwidas/DevPlus

| File / Folder | Purpose |
|---|---|
| `index.html` | Main dashboard — card grid, workflow status, chat panel |
| `ticket-manager/ticket-manager.html` | Ticket management app |
| `forecast/forecast.html` | Ticket forecasting / scheduling tool |
| `cocard/approve.html` | CoCard approve action page |
| `leads/merchant-form.html` | Merchant application form (public-facing) |
| `leads/decrypt-tool.html` | Merchant application viewer / decrypt tool |
| `email-date-request.html` | FM email template — date request (FM_Season_Annual_Creator) |
| `email-remove-hold.html` | FM email template — remove hold (FM_Season_Remove_Hold) |
| `email-close-account.html` | FM email template — close account (FM_Season_Close_Account) |
| `eula.html` | EULA for IMG Services FM Invoicing App |
| `privacy-policy.html` | Privacy policy for IMG Services FM Invoicing App |
| `icons/preview.html` | Icon preview utility for CoCard apps |
| `n8n/` | n8n workflow JSON exports |
| `airtable/` | Airtable schema reference |
| `CLAUDE.md` | Claude Code project instructions / tech spec |
| `DESIGN_SYSTEM.md` | CSS token reference |
| `SYSTEMS_INVENTORY.md` | This file — weekly auto-updated by scheduled agent |
| `farmers market-workflows-project-context.md` | FM workflow documentation |

---

## Airtable — Base: apppYzklXP1tsbWnF

| Table | Purpose |
|---|---|
| Companies | Merchant accounts |
| Contacts | Merchant contacts |
| Vendors | Equipment vendors |
| Equipment | Terminal / equipment inventory |
| ACH | ACH processing records |
| CoCard Pay Center | Pay center accounts |
| Pin Debit | Pin debit accounts |
| EBT | EBT accounts |
| VT_Gateway | Virtual terminal / gateway accounts |
| SwipeSimple | SwipeSimple accounts |
| Tickets | Support / task tickets |
| Ticket Tasks | Subtasks linked to tickets |
| FM Seasons | Farmers market season records |
| Merchant Application | Merchant onboarding applications |

---

## n8n CRM Workflows (exported to repo)

| Export File | Purpose |
|---|---|
| `n8n/crm/send-for-signature.json` | Send SignWell document from dashboard |
| `n8n/crm/signwell-completed.json` | Handle SignWell completion webhook |
| `n8n/crm/signwell-templates.json` | Fetch available SignWell templates |
| `n8n/crm/lead-created.json` | CRM lead created trigger |
| `n8n/crm/convert-lead.json` | Convert Lead to Customer |
| `n8n/crm/send-form.json` | Send Merchant Form to applicant |
| `n8n/crm/merchant-form-submit.json` | Handle Merchant Form submission |

---

## n8n Active Webhooks

| Webhook | Used By |
|---|---|
| `/webhook/search-companies` | Dashboard, Ticket Manager |
| `/webhook/search-contacts` | Ticket Manager |
| `/webhook/create-ticket` | Dashboard ticket form |
| `/webhook/create-recurring-ticket` | Ticket Manager on ticket close |
| `/webhook/n8n-status-proxy` | Dashboard workflow status cards |

---

## n8n Workflows — FM Season Automation

| Workflow | Purpose | Email Recipient |
|---|---|---|
| FM_Season_Annual_Creator | Creates new FM season tickets annually | FM market managers |
| FM_Season_Remove_Hold | Removes seasonal hold on account | Office (internal) |
| FM_Season_Close_Account | Closes FM account at season end | Office (internal) |

**4 FM Markets:** Military Avenue Inc (year-round), On Broadway Inc, City of Manitowoc, Downtown Green Bay

---

## Open Items / Backlog

- [ ] Fix `Code: Find FM Season` node — debug filterByFormula for 2026 seasons
- [ ] Swap Gmail sender: `kwidas@me.com` → `support@imgservices.com` in FM workflows
- [ ] QuickBooks production keys — waiting on Intuit compliance portal bug resolution
- [ ] Quote builder (`leads/quote-builder.html`) — in progress
