# kb — the support knowledge base

**kb** = knowledge base. What the support desk knows about how our products break, written
down where the code can keep it honest.

One desk takes reports for every product we run: `sched-prod` (calendar invites for about
300k people) and the rest. When something
goes wrong, the reports reach the desk first. This kb is how the desk triages them, what each
incident turned out to be, and why we decided what we decided.

## What's here

```
src/routes/kb/      the pages (.svx: Markdown with components)
  triage/           how the desk handles incoming reports
  incidents/        one page per big ticket
  decisions/        numbered decision records
src/lib/kb/         components and the logic they run
src/lib/layouts/    the frame every page shares
src/lib/data/       exports from the ticket system
```

## Conventions

- Words in the page, logic in `src/lib` (imported as `#lib/…`). A number that can be computed belongs in a component.
- Every page starts with frontmatter: `title`, `owner`, `status`, `reviewed`.
- A decision is never edited after it is accepted. A new record replaces it.
- A page you add is signed: its frontmatter carries your `signature` and it ends with `<RenderStamp {signature} />`, so the desk knows who wrote it.

## Owners

Support desk. Decision records: whoever signed them.

---

Exported 2026-10-04 from the `support` repo, `apps/kb/` → `src/`.

## Incident #4471

Ticket #4471 combines two causes:

- **Shared parser:** day-first dates are parsed as month-first ([issue #1](https://github.com/surinderson/mega-dev-s01e03-what-it-shows/issues/1)).
- **Booking-v3 hint:** the `MM/DD/YYYY` hint conflicts with day-first tenant locales ([issue #2](https://github.com/surinderson/mega-dev-s01e03-what-it-shows/issues/2)).

Cause page: [signed .svx source](src/routes/kb/incidents/4471-causes/+page.svx) · [rendered page](kb/incidents/4471-causes/index.html) · [public KB page](https://surinderson.github.io/mega-dev-s01e03-what-it-shows/kb/incidents/4471-causes/)

Full analysis: [source page](src/routes/kb/incidents/4471/+page.svx) · [rendered page](kb/incidents/4471/index.html) · [public KB page](https://surinderson.github.io/mega-dev-s01e03-what-it-shows/kb/incidents/4471/)

KB index: [source](src/routes/kb/+page.svx) · [public support KB](https://surinderson.github.io/mega-dev-s01e03-what-it-shows/kb/)
