# TakeMeter -- planning.md

## Community

My domain covers the TV show community. I source all of my comments from posts made on Reddit. I took posts from two subreddits: r/television and r/suits.
I chose this community because it fosters a lot of discourse, discussion, and analysis. How a person views a TV show is personal to their background and identity,
so many argue about why their opinion is the most correct or makes the most sense. However, not everyone includes sources in their takes or even has a valid foundation
for what they believe. This makes it easier to discern which posts have standing and which don't.

## Labels

### Label 1: Analysis

**Description:**
The post makes a structured argument backed by show context, show production context, or comparison. Evidence is specific and verifiable.

**Examples:**
- "...There's something much more fundamental at stake here. The years he spent undercover as Paul Lewis was a long and integral part of his life, and a significant piece of it was his relationship with Samia. When he returns from that assignment, he is supposed to cut all ties from that life, let go of that identity just like that, never mind if that's even possible.
If Martian simply ignores the existence of Samia (especially when she's nearby and in danger), if he treats his relationship as non-existent, the life he had been living in the past six years becomes a lie as well. And that's just too much for a person to bear, no matter how much he calls himself "one hundred percent identifiably nuts" as to do what's necessary for his job. You can't acknowledge one part of your past life and discard the rest. You either keep all of it alive, paying whatever price to do so, or you let the whole thing die.
So, to keep his mind sane and that self alive, Martian grasps at the one thing that lets him stay connected to that identity—Samia. Maybe that's why he's ready to go to such extreme lengths. He loves her and wants to protect her, we get that. But what he needs more is to keep Paul Lewis alive through her—otherwise what does he become?"
- "In Season 1, Episode 7 ('The Rule of Five Hundred'), there is a restaurant scene where Alexandra casually says: 'I’m British. All we do is travel the world and become experts in the places we visit.' It is delivered like light banter, almost playful, but it lands very differently if you actually sit with the history behind it. Because 'becoming experts' sounds neutral, almost admirable, but in reality a lot of that history is tied to extraction, control, reinterpretation of local systems, and long term cultural distortion. Not just learning about places, but actively reshaping them through power."

**Hard Edge Cases Example:**
Maybe an unpopular opinion but why do Entertainment shows feel necessary to include bad news such as current health issues. makes some people not be able to enjoy the shows anymore.

This example initially felt like a hot take, however, it is not asserting that something is true, it is reacting to an element of a TV show, making it a reaction.

### Label 2: Hot Take

**Description:**
A bold, confident opinion stated without supporting evidence. The claim might be true, but the post asserts rather than argues.

**Examples:**
- "Nathan Fielder made a show that's genuinely just vibes and collective confusion dressed up as deep commentary, and now it has a Peabody sitting next to actual journalism and documentary work. I'm not saying it's bad TV — it's weird and compelling — but we've officially entered an era where 'I don't fully understand it' gets mistaken for 'it must be brilliant.' Mad Men changed culture. The Rehearsal is just going to make people argue at brunch."
- "Maybe an unpopular opinion but why do Entertainment shows feel necessary to include bad news such as current health issues. Makes some people not be able to enjoy the shows anymore."

**Hard Edge Cases Example:**
The Good Place is fun but has no logic. There are a lot of reasons for this, like Chidi not caring about the fact that hell exists and there are indeed people being tortured there forever, but the main thing is no one getting onto the good place for 500 years (or whatever it was) especially after talking about Lincoln specifically being the only president to get in and the fact that the medium place exists at all (how the hell did she come close to getting into the good place at all in the 80s?). Fun show, nonsensical plot, baby's first philosophy ideas.

While this comment does use evidence taken from the show, it is not a substantial backing for the post's claim.

### Label 3: Reaction

**Description:**
An immediate emotional response to a specific event. Little to no argument — the post is expressing a feeling in the moment.

**Examples:**
- "I'm only on season 2 of this show but I only started a few days ago... I'm almost speechless. It's fucking incredible. Pirate intrigue, sea battles, incredible characters and plot momentum that hooks you so hard you can't stop watching.
The scale of this show, for a Starz original? Wtf, I don't understand how something at this scale got made outside of HBO at the time.
I thought the pilot was pretty good but episode 2 and 3 drag sufficiently that you might stop watching... But if you keep watching, holy shit, what a ride!!!"
- "Widow's Bay lives up to the hype. Just got done watching the first season. Didn't know much about the show besides horror, comedy, Dippold & Rhys.
There were more than a few moments throughout the series that felt genuinely unnerving like the party guests walking into the lake. The show also did a fantastic job of making the town just feel wrong.
The production team deserves a lot of credit. So much of the artwork seems okay at first glance. The longer you look at it, you realize it's wrong. Also the props which seem innocuous but also deeply weird (Daddy's Home! board game).
Matthew Rhys is probably a large reason I jumped on board. Ever since The Americans I've tried to check out everything he's involved in.
Tom is an amazingly well-rounded character brought to life. He's full of impotent rage & acts like he's a perpetually exposed nerve. There's so much sadness under the surface. You get the impression he's extremely careful about letting it out because he's worried he might not be able to stop."

**Hard Edge Cases Example:**
I Love Daniel Hardman. He was a genuinely great lawyer, played by a super underrated actor. I love how manipulative he was, I loved how cheeky he could be when he felt he was winning, and I wish he was the final big bad over Faye, bringing the show full circle. A truly intelligent antagonist whose ambitions always came to ruin because of his unquenchable thirst for revenge. I don't care about all the awful things he did, I loved him and rooted for him every time he was on screen. That deposition scene with Jessica? Chef's Kiss.

This comment includes evidence as to why the commentor feels a certain way about a character, however, it fits into reaction because it is not making an assertion about the show and instead stating a personal opinion on a character.

## Hard Edge Cases & Decision Rules
* **The Ambiguous Boundary:** Posts that pair a provocative statement with a single, cherry-picked detail or specific data point (sitting exactly on the line between *hot take* and *analysis*).
* **Decision Rule:** If a post provides clear, verifiable structural evidence that would independently sustain a logical argument even if the aggressive opinion framing were removed, label it `analysis`. If the evidence is purely decorative, cherry-picked for emotional effect, or too brief to form a cohesive argument, label it `hot take`.

## Data Collection Plan
* **Sources:** Public threads on r/television, r/moviecritic, and r/Letterboxd.
* **Quantity:** A target dataset of at least 200 public examples, aiming for a relatively balanced distribution (ideally between 25% and 40% per class).
* **Imbalance Strategy:** If any single label represents more than 70% of the dataset after initial passes, data collection will be paused to specifically query and harvest underrepresented categories (e.g., filtering subreddits explicitly by "Controversial" to find hot takes, or targeting deep discussion essays to find analysis) before finalizing the dataset.

## Evaluation Metrics
* **Metrics Chosen:** Macro F1-Score, Per-Class Precision, Per-Class Recall, and Cumulative Accuracy.
* **Justification:** While cumulative accuracy gives a general baseline of success, a multi-class task with potential imbalances requires Per-Class Precision and Recall. Precision ensures that when our model flags a post as an `analysis`, it actually contains structured evidence. Recall guarantees that we are not missing highly provocative text that belongs under `hot take`. The Macro F1-score averages these elements fairly across all three classes.

## Definition of Success
* **Minimum Viable Threshold:** A cumulative test accuracy of $\ge$ 70% and a Macro F1-score of $\ge$ 0.68 for the fine-tuned model.
* **Deployment Criteria:** To be considered useful as an automated community moderation or filtering tool, the model must out-perform a random guess baseline (33.3%) and meaningfully beat a zero-shot LLM baseline by at least 5% in classification accuracy.

## AI Tool Plan
* **Label Stress-Testing:** We used an LLM to generate borderline text blocks matching our criteria. This forced us to clarify that short, one-sentence complaints must be grouped under `hot take` or `reaction`, reserving `analysis` strictly for paragraphs containing structural layout or rationale.
* **Annotation Assistance:** Automated LLM pre-labeling was utilized on a subset of raw scraped text to create initial drafts. Every single pre-labeled row was then manually evaluated, verified, and re-annotated to ensure compliance with our strict taxonomy definitions.
* **Failure Analysis:** Post-evaluation misclassifications were passed to an LLM to help extract structural similarities (such as length limitations or punctuation indicators) that may have confused the model.

## Hard Annotation Decisions (Log)
During dataset creation, the following three specific examples proved challenging:
1.  *Post:* "Season 4 Episode 1 of Gilmore Girls stresses me out because they move Rory into her dorm in less than 24 hours. It's totally unrealistic." -> **Decision:** Classified as `reaction`. While it names a specific episode, it focuses entirely on the personal, anxious feeling elicited by the plot pacing rather than analyzing structural writing flaws.
2.  *Post:* "The pacing of House of the Dragon is terrible. The 10-year time jump completely ruined the structural buildup of the characters." -> **Decision:** Classified as `hot take`. It mimics analytical words ("structural buildup"), but it remains a brief, sweeping assertion without specific breakdown or scene examples.
3.  *Post:* "Every character in SUCCESSION is a horrible person and I cannot stand watching them destroy each other." -> **Decision:** Classified as `reaction`. It highlights an immediate personal emotional block toward viewing the content rather than assessing the show's thematic character work.

