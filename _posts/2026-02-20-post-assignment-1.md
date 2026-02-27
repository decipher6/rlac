---
title: "Assignment 1: Harry Potter Fan Fics Analysis"
date: 2026-03-22T15:34:30-04:00
categories:
  - blog
tags:
  - assignment
  - RLAC
  - update
---

# Harry Potter: Fanfics and JK Rowling

How much information can we get from a text without actually reading the text? Distant reading uses computational tools to find patterns across a corpus. It allows us to spot patterns that would be hard to spot through normal reading. This essay applies those methods to a corpus of five Harry Potter texts: two by JK Rowling and three fan fictions. The goal is to test whether differences between canon and fan fiction show up measurably in the language of the texts.


## Section 1: Corpus and Research Questions

### Corpus Selection

The corpus comprises five texts: *Sorcerer's Stone* and *Deathly Hallows* by JK Rowling, and three fan fictions. I chose the first and last books in the series deliberately. They span a decade of Rowling's writing and sit at opposite ends of the tone spectrum, giving a useful baseline for comparison.

The three fan fictions were chosen because each places Harry in a completely different environment. *Harry Potter Meets Harry Potter* by CaelynAilene keeps him in the wizarding world but in a post-war comedy where the characters discover fan fiction exists about them. *And I Will Find You* by lyingleia removes magic entirely. It shows Harry and Hermione as two British students at NYU. *Harry Potter: Djinn Awakened* by Wishmaster1983 is a crossover with the *Wishmaster* films and Netflix's *Lucifer*, where Harry's mother Lily uses a wish from a Djinn to save his life, a wish that has repercussions for both Harry and the world. The fan fictions are all doing something different, which means patterns that show up across all three are more likely to be meaningful than if the sample were three similar stories.

### Background and Hypotheses

Voyant Tool's Summary gives us a useful snapshot of each text's distinctive vocabulary. It gives us the words that are both frequent and unique to that document compared to the rest of the corpus.

![Figure 1: Voyant Summary — distinctive words in each text.](/assets/images/fig1_frequent_et_distinctive.png)

The results confirm the diversity of the corpus. *Sorcerer's Stone* is defined by "yeh," "hagrid," and "boy". The "yeh" resembles Hagrid's dialect and the repeated address of Harry as a child could result in "boy" being seen. *Deathly Hallows* is defined by "horcrux," "xenophilius," and "wand". These are objects and characters specific to the final war in Deathly Hallows. *HP Meets HP* surfaces "draco," "malfoy," and "laptop," that last word is a notable outlier among wizard stories. *Djinn Awakened* is defined almost entirely by its crossover characters: "greg," "djinn," "jack," "lance," "skullhammer." The NYU Alternate Universe's fingerprint is "clara," "nyu," "dorm," "phone," and "shop", which is a very mundane vocabulary. Even before diving into the text, this single view confirms that each text occupies a different world.

Three hypotheses going in: that *Philosopher's Stone* would have more food language than any other text, since Rowling is known to have used food as worldbuilding in a way fan writers rarely replicate; that violence vocabulary would link *Deathly Hallows* and *Djinn Awakened* more closely to each other than to *Philosopher's Stone*; and that character name distribution would shift noticeably across the fan fics.

---

## Section 2: Analysis and Findings

### Food Language and Worldbuilding

![Figure 2: R heatmap — food vocabulary across five texts.](/assets/images/fig2_food_heatmap.png)

The food heatmap is the finding I least expected to be this clean. Looking at the actual numbers: *Sorcerer's Stone* leads on chocolate (16), feast (7), beans (6), hungry (6), and cake (7). *Deathly Hallows* leads on food (21) and dinner (15), and notably has butterbeer (4) while *Sorcerer's Stone* has none. Which is believable as the drink is not introduced in the first book. *HP Meets HP* and the NYU Universe register zero across almost every food word. The NYU Universe has a single instance of chocolate and one of coffee, and nothing else. *Djinn Awakened* is the surprise as it has more food vocabulary than expected. For a dark crossover, 11 instances of dinner and 6 of butterbeer suggests Wishmaster1983 kept more of the wizarding world's texture than the other two fan fic authors did. But we also need to keep in mind that *Djinn Awakened* is a decisively long text compared to the other fan fics as seen in Figure 3 below.

![Figure 3: Voyant MicroSearch — Lengths of texts visualized.](/assets/images/fig3_lengths.jpg)

The broader pattern still holds though. In *Sorcerer's Stone*, food is how Rowling makes Hogwarts feel safe and real. The Contexts tool lets us do a little bit of close reading. When searching "feast" across the corpus we get results almost exclusively from *Sorcerer's Stone*, with phrases like "the Great Hall for the Halloween feast" and "the end-of-year feast." In *Deathly Hallows* the word appears only twice, and in a noticeably different register: "like a promise of a feast... He saw Ron's silver terrier." Food in book seven seems to be something Harry can only imagine and not experience. None of the fan fictions return a single feast result.

![Figure 4: Voyant Words in Context — contextual use of "feast" across the corpus.](/assets/images/fig3_context_feast.png)

The NYU Universe has essentially no food language because it has no wizarding world to build. That absence is meaningful. A realistic story set on a university campus doesn't need feasts to establish belonging, and lyingleia doesn't reach for them. The heatmap makes this invisible editorial choice suddenly visible.

Kestemont and Herman argue that machines can surface patterns in text but the interpretive work of deciding what those patterns mean stays entirely human. The heatmap shows the absence clearly, but explaining why it matters requires knowing what food actually does in Rowling's writing, and that comes from our own interpretation, not from the tool.

### Violence and Tone

![Figure 5: R heatmap — violence vocabulary across the corpus.](/assets/images/fig4_violence%20heatmap.png)

The violence heatmap confirmed the hypothesis, and the numbers are stark. *Deathly Hallows* dominates: 580 instances of "wand," 306 of "death," 194 of "dark," 113 of "magic," 101 of "dead," and 70 of "kill." *Djinn Awakened* follows a similar pattern: 249 instances of "magic," 84 of "wand," 69 of "dark," 57 of "death," and 45 of "war." *Sorcerer's Stone* sits in the middle, with 63 wand mentions and 62 of "dark" but only 10 instances of "death." The NYU Universe is zeroes almost across the board, which makes sense since it has no magic at all.

The most striking single number in the violence heatmap is "djinn" — 310 instances in *Djinn Awakened* and zero everywhere else. That one word captures exactly where the fan fiction breaks from everything in the corpus. Up to a point, *Djinn Awakened* and *Deathly Hallows* share a dark register. Both deal with death, dark forces, and war. But once Wishmaster1983's own mythology kicks in, the two texts diverge completely. "War" appears 45 times in *Djinn Awakened* and only 10 times in *Deathly Hallows*, which is also surprising — the fan fic is more explicitly war-focused in its vocabulary even though *Deathly Hallows* is the canonical war narrative.

This is a risk Underwood identifies in "The Risks of Distant Reading" — that surface patterns can mislead if you treat them as the whole story. The lexical overlap between *Djinn Awakened* and *Deathly Hallows* is real, but the two texts are doing very different things with that vocabulary. One is a war narrative about sacrifice. The other is a mythology-influenced crossover. The numbers show the overlap but close reading might reveal the underlying difference.

### Character Prominence

![Figure 6: Voyant Cirrus screenshot — prominent words across five texts.](/assets/images/fig5_word_cloud.png)

<iframe style='width: 626px; height: 393px;' src='https://voyant-tools.org/tool/Trends/?query=dumbledore&query=draco&query=harry&query=hermione&query=ron&corpus=8cc4f110c00ccf2076e3abe17597fcc3'></iframe>

*[Figure 7: Interactive Voyant Trends — explore character name frequency across all five texts.]*

The character name Trends graph shows Harry sitting far above everyone else across every text. But the gaps between the other characters shift in ways that directly reflect each author's focus.

In *HP Meets HP*, Draco rises to a frequency that nearly matches Ron and Hermione. In the Rowling novels the Draco line is nearly flat. Even in the Cirrus for the entire corpus Draco's prominence is not seen. CaelynAilene states in her author notes that she wrote a post-war Harry-Draco friendship, and the frequencies confirm it. This is what Adwetewa-Badu means when she says distant reading tools work best when the person using them already brings literary context to the analysis. Without knowing CaelynAilene set out to develop Draco, his name spike is just a number which could mean anything. Knowing it makes the finding meaningful.

The NYU adaptation shows something different. Ron's frequency drops to nearly zero while Hermione's climbs relative to Harry. The fanfic removes him entirely and reframes Harry and Hermione as the central relationship.

---

## Section 3: Critical Reflection

The most useful thing distant reading did here was make absence visible. The near-zero food language across all three fan fictions, Ron's disappearance in the NYU version, the low-frequency cells on the violence heatmap for some texts. These are all findings that only become clear when looking at multiple texts together. A cover-to-cover read of all five texts would have taken much more time and still wouldn't have revealed some of the findings of distant reading.

Underwood argues in "The Risks of Distant Reading" that these methods don't remove interpretation but instead move it upstream. Every choice made before running the analysis, which words to track, which texts to include, shaped what came out. The findings here only mean something because the corpus was chosen with a specific question in mind and the word lists were built around real hypotheses. Without that groundwork the tools wouldn't produce anything of value.

What the method can't do is explain the findings on its own. The numbers show that fan writers drop food language, but not whether that's intentional or just a side effect of focusing on the plot with constrained word count. The tools surface questions that close reading then has to answer. That's the most transferable lesson: use computational analysis to figure out where to look, then read closely to figure out what it means.

---

## Works Cited

Adwetewa-Badu, Ama Bemma. "Distant Reading: A Discussion with Ama Bemma Adwetewa-Badu" Interview by Kim Adams and Saronik Bosu.

Kestemont, Mike, and Luc Herman. "Can Machines Read Literature?" *Umanistica Digitale*, vol. 3, 2018. https://doi.org/10.6092/issn.2532-8816/8511

Underwood, Ted. "The Risks of Distant Reading." *Distant Horizons: Digital Evidence and Literary Change*. University of Chicago Press, 2019, pp. 143–169.