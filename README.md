# Handoff Ledger

An offline-first prototype for coordinating an MSP client handover across the outgoing provider, incoming provider, and client.

It tracks who owns each request, its due date, evidence reference, unresolved exceptions, and the agreed cutover/support boundary. The goal is a portable record that makes missing work and responsibility visible without requiring both MSPs to use the same PSA.

## Try the prototype

Try it [online](https://zyrixdevs.github.io/handoff-ledger/); drafts stay in your browser and are not uploaded to a Handoff Ledger server.

Open `index.html` in a modern browser. Data stays in that browser's local storage. Use **Export JSON** to move a working file between people and **Export handover** to create a Markdown packet. To try a pre-filled fictional scenario, download [`examples/sample-handover.json`](examples/sample-handover.json) and import it in the app. No server or dependencies are required.

## Scope and safety

- This is a workflow prototype, not a hosted shared workspace.
- Do not enter passwords, tokens, private keys, or other secrets. Store those in a client-approved password manager and add only a secure reference.
- Party acknowledgements are ordinary names and dates, not cryptographic signatures or legal attestations.
- The market and pricing hypothesis are unvalidated. Customer interviews must establish transition volume, effort, buyer, and willingness to pay before hosted product work.

## Why this exists

MSP community discussions describe repeated questions after handover packets are delivered and disagreement about overlap support and the moment responsibility changes. A commenter in a small-provider onboarding discussion also identifies missing owners and a lack of cohesive process. These are qualitative pain signals, not proof of market size or willingness to pay:

- [Transitioning MSP asking too many questions](https://www.reddit.com/r/msp/comments/1qkeam5/transitioning_msp_asking_too_many_questions/)
- [Offboarding standards](https://www.reddit.com/r/msp/comments/1roufo1/offboarding_standards/)
- [MSP client onboarding](https://www.reddit.com/r/msp/comments/1qzh4my/msp_client_onboarding/)

Generic checklist software is already available through products such as [ITFlow](https://docs.itflow.org/clients/onboarding), [ConnectWise PSA](https://www.connectwise.com/platform/psa/project-management), and [Hudu](https://www.hudu.com/tips_and_tricks_onboarding_offboarding). The hypothesis to test is whether neutral, cross-company coordination and a dated responsibility cutover are useful enough to warrant a dedicated tool.

See [the customer-discovery guide](docs/customer-discovery.md) for non-leading interview questions and evidence that would support or disprove the idea.

## Open source

MIT licensed. See [LICENSE](LICENSE).

## Static demo deployment

`.github/workflows/pages.yml` publishes only `index.html` to GitHub Pages when the default branch changes. Enable Pages with **GitHub Actions** as the build source in the repository settings. The app has no server-side storage; each visitor's draft stays in that browser's local storage.
