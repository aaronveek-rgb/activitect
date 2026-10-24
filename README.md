# Activitect: CL for Desmos & Amplify

Build custom activities in Amplify Classroom (formerly Desmos Classroom) with help from Claude. Describe the activity you want in ordinary words: what you're teaching and how students should work through it. Activitect plans the screens and components, writes the Computation Layer (CL) code for each one, and tells you how to test every step in the activity builder.

Activitect is an independent project by Aaron Veek, not affiliated with, endorsed by or sponsored by Desmos, Amplify or Anthropic.

It draws on a curated, read-only knowledge base of CL patterns, conventions and known pitfalls, and reproduces CL from it exactly. Anything it composes beyond a verified pattern is labeled unverified, with what to check. It works for experienced CL authors (terse and peer-level) and for teachers new to CL (one step at a time).

It can help with multiple choice, numeric and math input with equivalence checking, tables, graphs, choice grids, feedback and hints, randomized practice, rounds and levels, timed phases, and progress tracking across screens.

## What's in the plugin

- **Skill `cl-build-assistant`**: how Claude plans a build, when it looks things up in the knowledge base, and how it labels anything it adapts or composes.
- **Connector `activitect`** at `https://cl-drive-backend.vercel.app/api/mcp/public`: five read-only tools (List KB index, Search KB, Get KB entry, Read exemplar doc, List KB folder). No account or sign-in.

## Set up

1. Add the plugin from **Customize > Plugins**.
2. On the plugin's **Connectors** tab, connect `activitect`. There is nothing to sign in to.
3. Start a chat and describe the activity you want to build.

Without the plugin, for example on a Free plan: add `https://cl-drive-backend.vercel.app/api/mcp/public` as a custom connector under **Customize > Connectors** with no authentication, and upload the `skills/cl-build-assistant` folder as a ZIP under **Customize > Skills**.

## Example prompts

- I'm an experienced Desmos activity builder. Build one SBAC-style practice slide: three rounds of randomized problems with a streak counter, then a locked mixed round.
- I'm an experienced Desmos activity builder. Build a Tower of Hanoi activity: three pegs, students click to move disks, and it counts moves and says when they've solved it.
- I'm an experienced Desmos activity builder. My CL sets r = randomGenerator() and then uses r.randomInt(1,10), and it doesn't work. Why?
- How does the builder work under the hood?
- I'm an experienced Desmos activity builder. How do I make a summary slide that shows each student's progress from the earlier practice slides?

## What it sends and stores

The plugin runs no code on your computer. When Claude uses the connector, the server receives only what each tool call carries: search terms, knowledge-base entry IDs and document names. It never receives your conversation, your name or your account details, and it stores nothing from your requests. Its hosting provider, Vercel, keeps a technical log of each request for up to 30 days. At the end of a session Claude may offer an optional feedback form (Google Forms, https://docs.google.com/forms/d/e/1FAIpQLSdAQtS9u0NmhnyxwPcw5VGtZrIQREKRUU6WI2NK1sg8R93RNQ/viewform); nothing reaches it unless you open it and submit it yourself. Details are in [PRIVACY.md](PRIVACY.md).

## Limits

Claude can't see or change your Desmos or Amplify account; you paste the code into the activity builder yourself. Preview and test every activity before students use it. Terms of use are in [TERMS.md](TERMS.md).

## Support

Email aaronveek@gmail.com, or use the support page: https://cl-drive-backend.vercel.app/support

Every activity and pattern in the knowledge base comes from activities the author built.
