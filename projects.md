---
layout: default
title: Projects
permalink: /projects/
---
<section class="block wrap" style="border-top:none; padding-top:56px;">
  <span class="eyebrow">Work</span>
  <h2>Projects</h2>
  <div class="card-grid">

    <a class="entry-card tall" href="https://github.com/lcomet/UnifiedGuidelinesOntologyDevelopmentForIoP" target="_blank" rel="noopener">
      <div class="entry-main">
        <div class="entry-date">Ontology Development</div>
        <div class="entry-title">Unified Guidelines for Ontology Development for IoP</div>
        <p class="entry-desc">A practical, unified guideline for developing ontologies in the Internet of Production, letting Domain Experts and Knowledge Experts collaborate on semantic models without starting from scratch each time &mdash; built by studying and merging existing ontology-development methodologies.</p>
        <div class="entry-tags">
          <span class="chip">Ontology Engineering</span>
          <span class="chip">GitHub &#8599;</span>
        </div>
      </div>
    </a>

    <a class="entry-card tall" href="https://github.com/lcomet/IM-Application-Profiles" target="_blank" rel="noopener">
      <div class="entry-main">
        <div class="entry-date">Ontology Matching &amp; Mapping</div>
        <div class="entry-title">IM Application Profiles</div>
        <p class="entry-desc">Application profiles mapping domain-specific information models onto the IDS Information Model, aligning independently developed ontologies so data described under different schemas can be matched, related, and exchanged consistently across a Data Space.</p>
        <div class="entry-tags">
          <span class="chip">Ontology Matching</span>
          <span class="chip">IDS Information Model</span>
          <span class="chip">GitHub &#8599;</span>
        </div>
      </div>
    </a>

    <a class="entry-card tall" href="https://github.com/lcomet/OntologyAlignmentKGLab" target="_blank" rel="noopener">
      <div class="entry-main">
        <div class="entry-date">Ontology Matching &amp; Mapping</div>
        <div class="entry-title">KGLab: Evaluating Ontology Alignment Quality on BioPortal</div>
        <p class="entry-desc">A study evaluating how trustworthy the automatically-generated mappings between biomedical ontologies on BioPortal really are, using structural and terminological similarity metrics to flag matches that look correct by label but diverge semantically, benchmarked against a reference alignment.</p>
        <div class="entry-tags">
          <span class="chip">Ontology Alignment</span>
          <span class="chip">Biomedical Ontologies</span>
          <span class="chip">GitHub &#8599;</span>
        </div>
      </div>
    </a>

    <div class="entry-card tall" style="cursor:default;">
      <div class="entry-main">
        <div class="entry-date">Research</div>
        <div class="entry-title">Semantic Interoperability in Data Spaces</div>
        <p class="entry-desc">Ongoing research into how Data Spaces achieve interoperability by grounding shared vocabularies in semantics rather than fixed schemas &mdash; using ontologies, controlled vocabularies, and mapping/matching techniques so participants from different domains (Mobility, Industry 4.0, Agriculture, Culture) can exchange and understand each other's data without agreeing on a single rigid format up front.</p>
        <div class="entry-tags">
          <span class="chip">Data Spaces</span>
          <span class="chip">Semantic Interoperability</span>
          <span class="chip">Knowledge Graphs</span>
        </div>
      </div>
    </div>

    {% assign proj_posts = site.posts | where_exp: "p", "p.categories contains 'projects'" %}
    {% for post in proj_posts %}
    <a class="entry-card" href="{{ post.url | relative_url }}">
      <div>
        <div class="entry-date">{{ post.date | date: "%b %-d, %Y" }}</div>
        <div class="entry-title">{{ post.title }}</div>
      </div>
      <span class="arrow">&rarr;</span>
    </a>
    {% else %}
    <!-- Fallback: your original theme listed project entries the same way as
         blog posts (from _posts/). If your "my project" entry doesn't show up
         above, it likely isn't tagged with a "projects" category — add
         `categories: [projects]` to that post's front matter, or replace this
         whole fallback block with a manual list like the ones above. -->
    {% endfor %}
  </div>
</section>
