# Awesome AI Search Readiness [![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

Making websites discoverable inside AI-generated answers from ChatGPT, Perplexity, Claude, Gemini, and Google AI Overviews.

Also known as **GEO** (Generative Engine Optimisation), **AEO** (Answer Engine Optimisation), **LLMO** (LLM Optimisation), or **LLM SEO**. See the Terminology section below for what each term means.

Search is splitting in two. A growing share of buyer questions never reach a search results page — they end at an AI-generated answer with two or three citations. Most existing advice on this comes from vendors selling monitoring dashboards. A dashboard tells you you're invisible. It does not tell you what to fix. This list is biased toward resources that move you from monitoring the problem to fixing it. The bar for inclusion is high. The bar for the **Anti-Patterns** section is honest.

Start with **Foundations** if AI search is a new lens for you. Read **Anti-Patterns & Myths** before you spend money on tools. **Citation Tracking** and **Tools** are last on purpose — measurement matters less than the underlying fixes.

Tags: `[paid]` `[requires signup]` `[community]` `[2026]` `[2025]` `[uk]`.

## Contents

- [Terminology](#terminology)
- [Foundations](#foundations)
- [Standards & Protocols](#standards--protocols)
- [Content Structure](#content-structure)
- [Technical Optimisation](#technical-optimisation)
- [Citation Tracking](#citation-tracking)
- [Visibility Auditing](#visibility-auditing)
- [Research & Evidence](#research--evidence)
- [Case Studies](#case-studies)
- [Platform-Specific Guides](#platform-specific-guides)
- [Tools & Software](#tools--software)
- [Communities & Newsletters](#communities--newsletters)
- [Anti-Patterns & Myths](#anti-patterns--myths)

---

## Terminology

The same work goes by half a dozen names. They are used interchangeably in practice, but each has a slightly different origin and emphasis.

**GEO — Generative Engine Optimisation.** The current dominant term. Coined in 2023–2024 academic work and quickly adopted by industry. Specifically frames the problem around *generative* answer engines: ChatGPT, Perplexity, Claude, Gemini. If you have to pick one term in 2026, pick this one.

**AEO — Answer Engine Optimisation.** Predates GEO. Originally referred to optimising for Google's featured snippets and voice-assistant answers (Alexa, Siri) in the late 2010s. Re-applied to LLM answer engines after ChatGPT. Still common in SEO-native circles.

**LLMO — LLM Optimisation.** Less established but rising. Foregrounds the underlying model rather than the product surface. Useful when the conversation is about training data, RAG pipelines, or model-specific retrieval behaviour rather than end-user search UX.

**LLM SEO.** Informal. Frames the work as a continuation of classical SEO rather than a new discipline. Accurate enough for the ~70% overlap with traditional SEO, misleading for the parts that are genuinely different (sentence-level extraction, citation selection, conversational query patterns).

**AI Search Readiness.** The curator's preferred umbrella term — and the name of this list. Captures the actual buyer question ("is my site ready for AI search?") without committing to a specific acronym that may not survive the year.

**Practical guidance:** treat GEO and AEO as synonyms. Resources, tools, and people you'll meet use whichever term they entered the field with. If a resource draws a sharp distinction between the two, read the distinction carefully — it usually reflects the author's commercial positioning more than a genuine technical difference.

## Foundations

Start here if AI search is a new lens for you. These are the orientations, not the tactics.

- [Google: AI Overviews and your website](https://developers.google.com/search/docs/appearance/ai-features) - Google's own primer on how AI features pull from indexed content.
- [Perplexity: How sources are selected](https://www.perplexity.ai/hub/faq/how-does-perplexity-work) - First-hand explanation of citation behaviour from one of the major answer engines.
- [Learn AI Search](https://learningaisearch.com/) - Aleyda Solís's free, regularly-updated roadmap across GEO, AEO, and LLMO. Vendor-neutral.
- [A Reflection on SEO, GEO & AI Search in 2025](https://lilyraynyc.substack.com/p/a-reflection-on-seo-and-ai-search) - Lily Ray's year-end argument that GEO is mostly repackaged SEO. Useful corrective.
- [The AI Search Manual: Introduction](https://ipullrank.com/ai-search-manual/introduction) - Mike King's open book-length GEO manual. Chapter 1 is orientation; later chapters get tactical. Email serialisation `[requires signup]`.

## Standards & Protocols

The machine-readable layer. If AI tools cannot parse your site, no amount of clever content will rescue you.

- [Schema.org](https://schema.org/) - The vocabulary that lets you describe your business, content, and offerings in a way machines can read.
- [Schema.org / Article](https://schema.org/Article) - Markup for written content. Pair with `author`, `datePublished`, and `publisher` properties.
- [Schema.org / FAQPage](https://schema.org/FAQPage) - Marks up question-and-answer content. Often the highest-impact single change on a content site.
- [Schema.org / Organization](https://schema.org/Organization) - Tells AI tools what your business actually is, in machine-readable form.
- [Google: Structured data documentation](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data) - Reference for which schema types Google's pipeline actually consumes.
- [Google: Rich Results Test](https://search.google.com/test/rich-results) - Paste a URL or markup, get back what Google's parser sees. Use before and after every change.
- [JSON-LD](https://json-ld.org/) - Preferred format for structured data. Lives in a `<script>` tag; doesn't touch the visible page.
- [llms.txt proposal](https://llmstxt.org/) - Emerging spec for a site-level file pointing AI crawlers to your most important content.

## Content Structure

Writing for citation is not writing for SEO. AI tools extract sentences, not pages. Structure for clarity, answer specific questions, lead with the fact.

- [Google: Creating helpful, reliable, people-first content](https://developers.google.com/search/docs/fundamentals/creating-helpful-content) - Old guidance, still load-bearing. AI tools and classical search converge on the same content qualities.
- [How to create answer-first content that AI models actually cite](https://searchengineland.com/guide/how-to-create-answer-first-content) - Ten-step guide to writing the direct-answer paragraph AI engines extract.
- [LLM-Friendly Content: 12 Tips to Get Cited in AI Answers](https://www.onely.com/blog/llm-friendly-content/) - Onely's structural checklist: answer-first, listicles, tables, fact density. Vendor-adjacent but unusually concrete.
- [Information gain in SEO: what it is and why it matters](https://searchengineland.com/what-is-information-gain-seo-why-it-matters-429763) - Plain-English read on Google's information-gain patent. Anchors the "don't recycle, add" argument.
- [Breaking up is hard to do: chunking in RAG applications](https://stackoverflow.blog/2024/12/27/breaking-up-is-hard-to-do-chunking-in-rag-applications/) - Retrieval-side explainer that makes every other piece of structural advice make sense. AI engines extract sentences, not pages.

## Technical Optimisation

The unsexy fundamentals. AI crawlers and classical crawlers fail on the same things: slow pages, JavaScript-only content, broken mobile, blocked robots.

- [web.dev](https://web.dev/) - Google's reference for site performance, accessibility, and modern web fundamentals.
- [Core Web Vitals](https://web.dev/articles/vitals) - The metrics that quantify "your site feels slow." LCP, INP, CLS — learn them, measure them.
- [Google: robots.txt introduction](https://developers.google.com/search/docs/crawling-indexing/robots/intro) - If you block crawlers by accident, nothing else in this list matters.
- [Google PageSpeed Insights](https://pagespeed.web.dev/) - Free, gives a real-data + lab-data view. Run it before claiming your site is fast.
- [The rise of the AI crawler](https://vercel.com/blog/the-rise-of-the-ai-crawler) - Vercel + MERJ 500M-fetch dataset: GPTBot, ClaudeBot, PerplexityBot fetch JavaScript but never execute it.
- [AI Search and JavaScript Rendering — case study](https://www.gsqi.com/marketing-blog/ai-search-javascript-rendering/) - Glenn Gabe runs prompts at ChatGPT, Perplexity, and Claude against a JS-rendered site. None can read it.

## Citation Tracking

Tools that monitor whether ChatGPT, Perplexity, Claude, or Gemini cite your site for relevant queries. Useful for measurement; not a substitute for the underlying fixes.

The category is hot, not dormant. Every major name has shipped product and raised funding in 2025–2026. The dividing line is now pricing transparency rather than capability: several well-funded enterprise tools (Profound, Bluefish, Goodie, Conductor) have pulled public tiers and gone contact-sales-only. They are real products; they are not listed because the audience for this list cannot use them. Stick to the tools where you can read the price.

*Pricing and supported engines verified May 2026.*

- [HubSpot AI Search Grader](https://www.hubspot.com/aeo-grader/ai-search-tool) - Free, no-signup diagnostic showing how ChatGPT, Perplexity, and Gemini describe your brand.
- [Ahrefs AI Visibility Checker](https://ahrefs.com/ai-visibility-checker) - Free check across ChatGPT, Gemini, Perplexity, Copilot, and AI Overviews. No signup; paid from $398/mo.
- [Otterly.AI](https://otterly.ai/) - Continuous monitoring across the major AI engines. Transparent pricing from $29/mo. `[paid]` `[requires signup]`.
- [Peec AI](https://peec.ai/) - Prompt-based tracking with multi-region and Looker support. From €85/mo. `[paid]` `[requires signup]`.
- [AthenaHQ](https://athenahq.ai/) - YC-backed AEO platform across 8+ engines with prompt-volume estimation. From $95/mo annual. `[paid]` `[requires signup]`.

## Visibility Auditing

Methodologies, frameworks, and checklists for auditing a site's AI search readiness — including the curator's own service.

- [Website & AI Search Readiness Audit](https://contra.com/VictorOsondu/) - Curator's paid audit. Listed for transparency, not as a recommendation over alternatives. `[paid]`.
- [AI Search Content Optimization Checklist](https://www.aleydasolis.com/en/ai-search/ai-search-optimization-checklist/) - Aleyda Solís's free Google Sheet covering crawlability, chunks, citation-worthiness, measurement. Updated April 2026.
- [The AI Search Manual](https://ipullrank.com/ai-search-manual) - Mike King's book-length open manual on Relevance Engineering. Free to read.

## Research & Evidence

Academic papers, benchmarks, and studies. The antidote to vendor-claim inflation. Where a study is cited often but the original is hard to find, link the original — not the explainer.

- [GEO: Generative Engine Optimization (Aggarwal et al., KDD 2024)](https://arxiv.org/abs/2311.09735) - Princeton-led paper that coined the field. Reports up to **40%** visibility uplift, not the widely-misquoted 115%.
- [Evaluating Verifiability in Generative Search Engines](https://arxiv.org/abs/2304.09848) - Stanford audit (Liu, Zhang, Liang, EMNLP 2023): only 51.5% of generated sentences are fully supported by their citations.
- [GEO-Bench dataset](https://huggingface.co/datasets/GEO-Optim/geo-bench) - 10k-query open benchmark behind the Princeton paper. Run your own experiments.
- [GEO-Optim/GEO reference implementation](https://github.com/GEO-optim/GEO) - The Princeton paper's official code and benchmark harness. Reproduce the numbers rather than trusting them. `[2024]`.
- [CC-GSEO-Bench: A Content-Centric Benchmark](https://arxiv.org/abs/2509.05607) - Creator-centric successor benchmark (Chen et al., 2025) scoring sources on exposure, credit, impact, readability, trust.
- [AutoGEO](https://github.com/cxcscmu/AutoGEO) - CMU framework (ICLR 2026) that learns engine preferences and rewrites content. Research-grade; don't aim it at production. `[2026]`.
- [The crawl-to-click gap](https://blog.cloudflare.com/crawlers-click-ai-bots-training/) - Cloudflare network-level data: Anthropic crawled ~38,000 pages per referral in July 2025.
- [Google users are less likely to click on links when an AI summary appears](https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/) - Pew Research panel (n=900): AI Overviews roughly halve click-through to traditional links (8% vs 15%).
- [Awesome-GEO](https://github.com/DavidHuji/Awesome-GEO) - Community-curated bibliography of GEO research: ranking manipulation, multi-source corroboration, open protocols. A map of the literature. `[community]`.

## Case Studies

Real, verifiable examples of brands gaining or losing AI visibility — with enough detail to learn from.

This section is deliberately short. Indie engineering writeups with dated screenshots barely exist in this category yet; vendor "case studies" don't clear the bar. The strongest sources right now are regulatory filings, court documents, earnings calls, and first-party numbers from named operators — places where the evidentiary cost of lying is high enough to trust the numbers. One caveat on the gains: when a company reports its own growth figures, trust the direction more than the magnitude. PRs welcome when better sources appear.

### Gains

- [Shopify Q1 2026 earnings call](https://www.fool.com/earnings/call-transcripts/2026/05/05/shopify-shop-q1-2026-earnings-transcript/) - AI-driven traffic up 8× YoY, orders from AI searches up ~13×; structured catalog data converts 2× better.
- [Vercel: ChatGPT referral share of new signups](https://x.com/rauchg/status/1910093634445422639) - CEO's first-party numbers: under 1% of signups in September 2024, 4.8% by March 2025, 10% by April.

### Losses

- [Chegg, Inc. v. Google LLC — antitrust complaint](https://www.courtlistener.com/docket/69668109/chegg-inc-v-google-llc/) - Chegg's lawsuit attributes a 49% YoY drop in non-subscriber traffic (Jan 2024 → Jan 2025) to AI Overviews.
- [DMG Media submission to the UK CMA on Google's AI Overviews](https://assets.publishing.service.gov.uk/media/68a5aa50a6acbbc7fb96a3b2/DMG_Media.pdf) - UK regulator submission: desktop CTR fell from 25.2% to 2.8% (−89%) when an AI Overview appears. `[uk]`.
- [Penske Media Corporation v. Google LLC — antitrust complaint](https://www.courtlistener.com/docket/71332589/penske-media-corporation-v-google-llc/) - Rolling Stone and Variety owner's federal filing: affiliate revenue down more than a third since AI Overviews scaled.
- [Stack Overflow is almost dead](https://blog.pragmaticengineer.com/stack-overflow-is-almost-dead/) - Gergely Orosz charts Stack Overflow's own data: monthly questions back at 2009 launch levels by May 2025.

## Platform-Specific Guides

How each major answer engine selects, cites, and ranks sources — straight from the platform where possible.

### ChatGPT (OpenAI)

- [OpenAI: ChatGPT search](https://openai.com/index/introducing-chatgpt-search/) - OpenAI's official explanation of how ChatGPT search retrieves and cites web content.
- [AI Search Architecture Deep Dive](https://ipullrank.com/ai-search-manual/search-architecture) - iPullRank's architectural teardown of ChatGPT, Bing Copilot, Perplexity, and Gemini retrieval pipelines. Includes diagrams.

### Microsoft Bing & Copilot

Bing's index powers Copilot *and* ChatGPT's web search, so Bing visibility is upstream of both. This is the one engine that reports your AI citations first-party.

- [Bing Webmaster Tools: AI Performance report](https://blogs.bing.com/webmaster/February-2026/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview) - Microsoft's first-party data on when Copilot and Bing AI answers cite your pages, plus the queries that grounded them. `[2026]`.
- [Keeping content discoverable with sitemaps in AI-powered search](https://blogs.bing.com/webmaster/July-2025/Keeping-Content-Discoverable-with-Sitemaps-in-AI-Powered-Search) - Bing's own guidance on staying crawlable and fresh for the index behind Copilot and ChatGPT. `[2025]`.

### Perplexity

- [Perplexity Hub: FAQ](https://www.perplexity.ai/hub/faq) - Official answers on sources, citations, and how content is ranked.
- [How Perplexity AI Answers Work: retrieval, ranking, citation pipeline](https://ziptie.dev/blog/how-perplexity-ai-answers-work/) - Six-stage walk-through grounded in Perplexity's own publications and arXiv work. Vendor-affiliated; citations stand up.

### Claude (Anthropic)

- [Anthropic: Claude can now search the web](https://www.anthropic.com/news/web-search) - Announcement and behaviour notes for Claude's web search.
- [How Claude Picks Sources: a technical breakdown](https://www.oltre.ai/blog/how-claude-picks-sources-technical-breakdown-claude-citations/) - Analysis showing 86.7% overlap between Claude citations and Brave Search results — Brave visibility is the gating factor.

### Google Gemini & AI Overviews

- [Google Search: Generative AI in Search](https://blog.google/products/search/generative-ai-google-search-may-2024/) - Google's framing of how AI Overviews integrate with classical search.
- [How AI Mode Works and How SEO Can Prepare](https://ipullrank.com/how-ai-mode-works) - Mike King reads the Google patents behind AI Mode: query fan-out, passage-level retrieval, ranking. Patent-grounded, not vibes-grounded.

## Tools & Software

Tools you can actually run. Free first, paid clearly labelled. Inclusion is not endorsement of pricing or roadmap — it's a statement that the tool currently does what it claims.

- [Schema Markup Validator](https://validator.schema.org/) - The official schema.org validator. Strict syntactic check; use after Google's Rich Results Test.
- [Schema Markup Generator (Merkle / TechnicalSEO)](https://technicalseo.com/tools/schema-markup-generator/) - Free form-based JSON-LD generator from Merkle (dentsu). Covers Article, Product, FAQ, LocalBusiness, HowTo, and 100+ local subtypes.
- [Schema.dev Builder](https://schema.dev/) - Free JSON-LD builder, tester, and deployer. More schema types than Merkle's; paid tier for managed deployment.
- [AI Crawler Simulator](https://keyword.com/ai-crawler-simulator/) - Free, no-signup tool that hits your URL with the user-agents of 12 AI crawlers. Returns per-bot status codes.
- [CrawlerCheck](https://crawlercheck.com/) - Free analyser of robots.txt, meta robots, and X-Robots-Tag. Tests configuration; complements AI Crawler Simulator.
- [LLMrefs AI Crawlability Checker](https://llmrefs.com/tools/ai-crawl-checker) - Free crawl test that shows the actual text GPTBot extracts after JS is stripped.
- [SiteTest.ai](https://sitetest.ai/) - Free A–F GEO grade across 168 checks. Paid tiers from $4.99 add per-platform scores. Verify still live.
- [Firecrawl llms.txt generator](https://llmstxt.firecrawl.dev/) - Free, open-source generator for `llms.txt` and `llms-full.txt`.
- [Screaming Frog SEO Spider](https://www.screamingfrog.co.uk/seo-spider/) - UK-built desktop crawler. Spoofs AI bot user-agents; free up to 500 URLs, £199/year above. `[uk]` `[paid]`.

### Open-Source

Repos you can read, run, and fork. Vetted for a real licence, recent commits, and a core function that works without a paid key. Self-hosted monitoring exists but is mostly immature — audit-and-fix tooling clears the bar more often than dashboards.

- [eGEOagents](https://github.com/mverab/eGEOagents) - CLI and Claude Code toolkit for content audits, rewrites, and JSON-LD; its ranking score is a stated proxy. `[2026]`.
- [Gego](https://github.com/AI2HU/gego) - Self-hosted GEO tracker: scheduled prompts across OpenAI, Anthropic, Gemini, Perplexity, and Ollama, with a citation dashboard. `[2026]`.
- [GEO Optimizer Skill](https://github.com/Auriti-Labs/geo-optimizer-skill) - Audits AI visibility and tracks whether ChatGPT, Perplexity, Gemini, and AI Overviews cite you; CLI, Python, MCP. `[2026]`.
- [nuxt-llms](https://github.com/nuxt-content/nuxt-llms) - Official Nuxt module that auto-generates `llms.txt` and `llms-full.txt` from your site content. `[2026]`.
- [vitepress-plugin-llms](https://github.com/okineadev/vitepress-plugin-llms) - Generates `llms.txt` and LLM-friendly Markdown output for VitePress documentation sites. `[2026]`.

## Communities & Newsletters

Where practitioners actually compare notes. Marketing thought-leadership Substacks excluded unless they ship original evidence.

- [Growth Memo](https://www.growth-memo.com/) - Kevin Indig's research-led newsletter: original UX studies, clickstream analyses, citation-pattern work. `[community]`.
- [SEOFOMO](https://seofomo.co/) - Aleyda Solís's weekly curated digest of SEO + AI-search news. ~40K subscribers. `[community]` `[requires signup]`.
- [Lily Ray on Substack](https://lilyraynyc.substack.com/) - Original analyses of AI-content backfire patterns, AI Overview anomalies, and listicle gaming. `[community]`.
- [r/TechSEO](https://www.reddit.com/r/TechSEO/) - Subreddit where AI-search technical questions get real practitioner answers. Skip the bigger SEO subs. `[community]`.

## Anti-Patterns & Myths

The most useful section in this list. Read before you spend.

**"AEO is just SEO with a new name."**
Overlap is real — speed, structure, and clarity help both. But the unit of value is different. SEO ranks pages; AEO surfaces sentences. Writing optimised for one is sometimes wrong for the other. Treat them as related, not identical.

**"More content = more citations."**
The opposite, often. Thin, repetitive content dilutes the signal of the genuinely useful pages on your site. AI tools optimise for the page that best answers a question, not the site with the most pages. Prune ruthlessly.

**"The monitoring tool will tell us what to fix."**
Monitoring tools tell you you're invisible. They rarely tell you why, and never specifically. Diagnosis is a different category of work than measurement — don't confuse them.

**"We need to game the AI before competitors do."**
The interventions that worked against early Google ranked sites for a year before Google patched them. The interventions that work against AI answer engines are the boring ones: clarity, structure, evidence, schema. Boring scales; clever doesn't.

**"AI is going to replace search, so SEO is dead."**
SEO is changing, not dying. Classical search still drives most of the traffic on most sites in 2026. The right posture is *and*, not *or*: keep ranking, also get cited.

**"Vendor whitepapers count as evidence."**
A whitepaper from a tool company showing that their tool helps is not evidence. It is marketing. Look for independent studies, public datasets, or before/after data from someone with no financial interest.

**"Schema markup is enough on its own."**
Schema is necessary infrastructure but does not, on its own, move AI citations on pages already established enough to rank. [Ahrefs ran a difference-in-differences on 1,885 pages adding schema](https://ahrefs.com/blog/schema-ai-citations/) between August 2025 and March 2026 — Google AI Overview citations fell 4.6%, AI Mode and ChatGPT moved 2.4% and 2.2%, both statistically indistinguishable from zero. Audits keep turning up pages with perfect FAQPage markup that don't get cited, and pages with no schema at all that do. Schema makes you eligible. The content beneath it decides whether you're chosen.

**"Block AI crawlers to protect your content."**
Blocking AI crawlers protects you from being trained on; it also makes you invisible to the AI search engines your buyers now use. [Cloudflare flipped its default to block AI crawlers on 1 July 2025](https://blog.cloudflare.com/content-independence-day-no-ai-crawl-without-compensation/), and most site owners who clicked that toggle did so without realising that `OAI-SearchBot`, `PerplexityBot`, and `Google-Extended` do retrieval for live answers, not training. You can refuse training and still allow citation — but only if you read your robots.txt carefully and know which user-agent does which job. The right posture is policy, not panic.

**"Long-form content always wins."**
AI engines cite sections, not posts — extractable structure beats word count. [Ahrefs' analysis of 560,000+ AI Overviews](https://ahrefs.com/blog/short-vs-long-content-in-ai-overviews/) found 53.4% of citations go to pages under 1,000 words; the correlation between word count and citation position is effectively zero. The model isn't reading your essay; it's scanning for a chunk that answers a question without needing the chunks around it. A well-structured 800-word piece routinely outperforms a meandering 3,000-word one. The reason is mechanical, not aesthetic.

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md). Opinionated curation, vendor pitches closed without drama.

## Footnotes

Curated by Victor Osondu, founder of [AI Tutorium](https://aitutorium.com). Victor audits websites for AI search readiness as a paid service — the audit is listed under Visibility Auditing above. The audit and this list share a methodology: structured data, citation-friendly content, technical fundamentals, in that order.
