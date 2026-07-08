---
layout: default
title: "Ontology development, and where AI tools actually help"
date: 2026-07-08
categories: [blog]
---

<section class="block wrap" style="border-top:none; padding-top:56px; max-width:760px;">

<p>Ontology development has a reputation for being slow, and it's earned. Building a good ontology means getting a Domain Expert and a Knowledge Engineer to agree on what a "vehicle," a "process," or an "event" actually means in a specific context &mdash; then encoding that agreement precisely enough for a machine to reason over it. Every step of that has a bottleneck, and lately I've been thinking hard about which of those bottlenecks AI tools can genuinely help with, and which ones they can't.</p>

<h2>The recurring bottlenecks</h2>

<p>A few problems show up in almost every ontology project I've worked on, regardless of domain:</p>

<p><strong>The knowledge acquisition gap.</strong> Domain Experts know the domain but not formal semantics; Knowledge Engineers know OWL and description logics but not the domain. A huge share of project time goes into just translating between the two, and a lot gets lost in that translation.</p>

<p><strong>Reuse instead of reinvention.</strong> There's rarely a good reason to model "location" or "agent" from scratch when a dozen well-maintained ontologies already do it. But finding the right existing terms to reuse, and understanding whether their intended semantics actually match your use case, takes real effort &mdash; it's a search and comprehension problem before it's a modelling problem.</p>

<p><strong>Ontology matching and alignment.</strong> The moment two systems need to interoperate, someone has to work out which classes and properties in one ontology correspond to which in the other &mdash; not just by label, but by actual meaning. Two ontologies can both have a class called <code>Component</code> that mean completely different things. This gets harder, not easier, as the number of participating systems grows, which is exactly the situation Data Spaces create.</p>

<p><strong>Keeping it consistent as it grows.</strong> Ontologies are living artifacts. As new terms get added by different contributors over time, subtle inconsistencies creep in &mdash; overlapping classes, contradictory axioms, orphaned terms nobody uses. Catching these requires both logical validation and a working memory of everything already in the model.</p>

<p><strong>Documentation nobody has time to write.</strong> Competency questions, term definitions, usage examples &mdash; the artifacts that make an ontology usable by someone other than its author are usually the first thing cut when a project runs out of time.</p>

<h2>Where AI tools are actually useful</h2>

<p>None of this is solved by throwing a language model at "generate me an ontology." But several of these bottlenecks are narrow enough that current AI tools give real, checkable leverage:</p>

<p><strong>Drafting from domain text.</strong> Given a set of domain documents, an LLM can propose a first-pass list of candidate classes, properties, and relationships, along with the sentences that justify them. This doesn't replace the Domain Expert / Knowledge Engineer conversation, but it gives that conversation something concrete to react to instead of starting from a blank page. Reacting to a draft is a much easier task for a Domain Expert than authoring formal structure from scratch.</p>

<p><strong>Surfacing candidates for reuse.</strong> Instead of manually searching ontology catalogues, you can point a model at your competency questions and a set of established ontologies and ask it to propose which existing terms are plausible matches, with its reasoning. A human still has to verify the semantics hold up, but the search space shrinks dramatically.</p>

<p><strong>Assisting ontology matching.</strong> This is close to my own work on application profiles for the IDS Information Model: aligning independently developed models is fundamentally about comparing meaning, not just labels. Embedding-based similarity and LLM-assisted reasoning over definitions and context can propose candidate mappings between classes and properties across ontologies &mdash; again, as candidates for a human to confirm, not as ground truth.</p>

<p><strong>Consistency and gap checking.</strong> Language models are decent at reading through a large set of axioms and flagging things that look off &mdash; a class defined two different ways, a property used inconsistently, a term that seems to duplicate another. Combined with a proper reasoner for the formal logic, this catches issues earlier and cheaper than a manual review pass.</p>

<p><strong>Generating the boring-but-necessary documentation.</strong> Turning a formal ontology into plain-language definitions, usage examples, or a first draft of competency questions is exactly the kind of translation task language models are good at, and it's usually the artifact that got skipped for lack of time.</p>

<h2>Where I'd stay cautious</h2>

<p>The common thread in all of the above is that AI tools are good at proposing and summarizing, not at deciding. A model can suggest that two classes probably align, or that a term is missing, but it doesn't understand your domain's actual commitments &mdash; the reasons your team chose one modelling decision over another. Handing that decision to a model, rather than to the Domain Expert and Knowledge Engineer working together, is how you end up with an ontology that looks coherent and isn't.</p>

<p>This is also where I think a lot of the "AI will automate ontology engineering" framing gets it backwards. The bottleneck was never typing out axioms quickly. It was building shared, correct understanding between people who see the domain differently. AI tools can remove a lot of the friction around that process &mdash; drafting, searching, checking, documenting &mdash; but the understanding itself still has to be built by the people who need to trust the result.</p>

<p>I explored a related version of this question in <a href="https://arxiv.org/abs/2310.08365" target="_blank" rel="noopener">a recent paper on using LLMs for biomarker knowledge graph construction</a>, and I think the lesson generalizes well beyond biomedicine: treat the model as a fast, sometimes-wrong research assistant, keep the verification step non-negotiable, and you get a genuinely useful speed-up without giving up rigor.</p>

</section>
