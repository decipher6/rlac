---
title: "Assignment 2: Comparing Stylo with TF-IDF for a Science Fiction Corpus"
date: 2026-03-22T15:34:30-04:00
categories:
  - blog
tags:
  - assignment
  - RLAC
  - Stylo
  - TF-IDF
  - Science Fiction

---

# Comparing Stylo with TF-IDF for a Science Fiction Corpus

Distant reading is a way of analyzing literature using computers instead of reading every word closely. In this essay, I use two methods on a set of science fiction texts from Project Gutenberg. The first is the stylo package in R, which looks at how often certain words appear to detect writing style. The second is a TF-IDF visualization using PCA at 500 most frequent words, which looks at what words are unique to each text. As Ted Underwood argues in The Dangers of Distant Reading, these methods are useful but they need careful interpretation. The numbers alone cannot tell you what they mean. They need to be interpreted in the context of the corpus and the research questions.

The corpus has eighteen texts by six authors, written between the late 1800s and the early 1960s. The authors are H. G. Wells, Philip K. Dick, Andre Norton, Leigh Brackett, Henry Kuttner, and Marion Zimmer Bradley. There is also one co-authored text, The Black Kiss, written partly by Kuttner and partly by Bloch.

The texts are quite different from each other. Wells wrote Victorian science fiction about alien invasion and moral philosophy. Dick wrote short stories about Cold War and robots. Norton wrote about space exploration. Brackett mixed science fiction with adventure and romance. Kuttner wrote across several styles, serious adventure to satire. Bradley wrote planetary romance as well as fiction. This variety raises a simple question: will the computer group these texts by what they are about, or by who wrote them? The two methods answer this question in different ways, and comparing them is where things get interesting.

## Section 1: Stylometry

First, we will look at stylometry. Stylometry looks at how often authors use common words like "the," "and," and "but." These words are not really about any topic. They just reflect how a person naturally writes. The idea is that every writer has unconscious habits in how they structure sentences and choose small connecting words. These habits stay consistent across different stories, even when the topics change completely. I used a hierarchical cluster analysis and a Bootstrap Consensus Tree to test this.

<figure>
  <img src="../../assets/images/CA_500MFW.png" alt="Cluster Analysis 500 MFW">
  <figcaption>Figure 1: Cluster Analysis with 500 most frequent words.</figcaption>
</figure>

The clearest finding is that texts by the same author tend to group together. Philip K. Dick's three stories (Second Variety, The Variable Man, The Defenders) form a tight cluste. Andre Norton's three texts (Plagueship, Star Hunter, Voodoo Planet) do the same. This supports the basic idea behind stylometry: that writing style is consistent enough to detect even when the stories are about different things. Dick's stories seem to be quite different in terms of plot, but his way of writing stays recognizable and is clustered together.

Not every author clusters this neatly. Leigh Brackett's works are more spread out. Two of her texts group together, but The Blue Behemoth drifts closer to Kuttner's work. This might be because both authors were writing in similar genres or following certain trends popular at that time and picked up some of the same stylistic attributes. It could also mean that Brackett's style simply varies more than some of the other authors in the corpus.

Another outlier is Wells's The Salvaging of Civilization. It sits far from his other two texts. The reason is simple: it is a non-fiction essay, not a novel. Essays and stories use words in different ways, and the model picks up on this. Even though Wells wrote all three texts, the genre difference is strong enough to separate this one from the rest.

<figure>
  <img src="../../assets/images/CA_100MFW.png" alt="Cluster Analysis 100 MFW">
  <figcaption>Figure 2: Cluster Analysis with 100 most frequent words.</figcaption>
</figure>

Comparing the 100 MFW and 500 MFW analyses is also useful. At 100 MFWs, the clusters are a little less stable. At 500 MFWs, the groupings become clearer and more consistent. This makes sense because more words give the model more information to work with. However, there is a tradeoff: the more words you include, the more likely some of them reflect the topic rather than pure writing style.


<figure>
  <img src="../../assets/images/BCT_delta.png" alt="BCT_delta">
  <figcaption>Figure 3: Bootstrap Consensus Tree.</figcaption>
</figure>

The Bootstrap Consensus Tree helps with this problem. It runs the clustering many times across different samples and shows which groupings appear consistently. Dick and Norton's clusters are stable across these runs. Brackett's The Blue Behemoth is not, which tells us to treat its positioning with some caution.

The Black Kiss clusters near Kuttner's solo work. This suggests that one author's style dominated, or that the model just cannot separate two voices mixed together in one text.

The wordlist confirms that the clustering is driven almost entirely by function words like "the," "and," "he," and "was." These words carry no meaning on their own. They just reflect grammatical habits. However, toward the bottom of the list, a few content words appear: character names like "dane" and "stark," and body-part words like "eyes," "face," and "hand." These suggest that at higher MFW counts, the model starts picking up on topic and character as well as pure style. The presence of "men," "man," and "world" also reflects something about the corpus itself: most of these stories center on male protagonists operating in large-scale settings, which was typical of 1950s science fiction regardless of whether the author was male or female.

## Section 2: TF-IDF

<figure>
  <img src="../../assets/images/pca.png" alt="PCA plot of TF-IDF scores">
  <figcaption>Figure 4: PCA plot of TF-IDF scores.</figcaption>
</figure>

TF-IDF works differently from stylometry. Instead of looking at common function words, it finds words that are especially distinctive to each text compared to the rest of the corpus. If a word appears a lot in one text but rarely in others, TF-IDF gives it a high score. The PCA plot then shows which texts are similar based on this kind of vocabulary. This makes it more sensitive to what a text is actually about rather than how it is written.

The two methods agree on the clearest outliers. The Salvaging of Civilization sits far to the right of the TF-IDF plot, alone and separated from everything else. This suggests that it is using specefic words that are not common to the other texts. These could be scientific words or other domain specefic terms that are not normally used. Norton's texts form a loose group in the lower-right of the plot. Dick's three texts sit close together in the lower-center. Their shared focus on machines, war, and paranoia keeps them near each other in both methods.

Another interesting observation is that Marion Zimmer Bradley's Jackie Sees a Star is the most isolated text in the entire TF-IDF visualization. It sits in the far upper-left, far from everything else. And in the stylometric analysis, Zimmer Bradley's other works cluster together, except Jackie Sees a Star, which is on a separate branch. We would require context about the specefic text to understand why this is the case. Jackie Sees a Star is a children's story with a very ordinary Earth setting. It has completely different vocabulary from the rest of the corpus, which is full of spaceships and alien planets. TF-IDF catches this immediately. So does stylometry pick up on it, because the grammar patterns change depending on whether you are writing for children or adults. This is exactly what Underwood means when he says computational results need interpretation.

Kuttner's The Ego Machine shows a patternof disagreement between the two methods. In the stylometric analysis it clusters with Kuttner's The Black Kiss. But in the TF-IDF plot it ends up far to the left. The Ego Machine is a comedic and satirical story, very different in tone from Kuttner's other work. The humor and satire bring in a different set of words, and TF-IDF picks up on this difference in a way that stylometry does not. This is a good example of how TF-IDF can catch genre variation within a single author's output.

The Black Kiss also moves between the two methods. Stylometrically it sits with Kuttner. In the TF-IDF plot it moves closer to Dick's group. Its gothic and horror vocabulary may connect it thematically to Dick's work, which is considered to be darker fiction, even though the writing style still feels like Kuttner. Depending on which method you use, the text belongs to a different neighborhood in the corpus.

Brackett's texts stay scattered in both analyses. None of her three works group tightly under either method. This probably reflects the fact that she wrote across several different styles and tones, so no single pattern holds across all three texts.

Stylo is good at finding an author's style. It groups texts by who wrote them, even when the topics are different. But it might not catch differences in tone or genre within one author's work that well.

TF-IDF is good at finding thematic and content similarity. It picks up on what a text is actually about. But it can be inconsistent when an author writes across many different topics. It also tends to isolate unusual texts more aggressively, as seen with Jackie Sees a Star and The Ego Machine.

Using both together gives a clearer picture than either one alone. Jackie Sees a Star is a good example. Stylo says it belongs with Zimmer Bradley's work. TF-IDF says it is unlike anything else in the corpus. Both statements are true. They just describe different things about the same text. As Underwood argues, the value of distant reading is not in the patterns themselves, but in the questions they push you to ask about why those patterns exist. When we saw the outliers, we asked why they were outliers. We did not just accept the numbers as fact. Diving deeper into what the books were about and the themes the authors work with gives us a better understanding of why the outliers are outliers.

To conclude, looking at eighteen science fiction texts through two computational methods shows both the usefulness and the limits of distant reading. When both methods agree, like with Dick and Norton clustering together or Wells's essay standing apart, those results feel reliable. When they disagree, like with Jackie Sees a Star or The Ego Machine, that disagreement points toward something worth looking at more closely.

These texts were mostly written for pulp magazines in the 1950s, for readers living through the Cold War and the early nuclear age. Dick's stories about paranoid machines, Norton's survival adventures in space, and Brackett's planetary romances all come from the same historical moment but respond to it in different ways. Computational tools can show us patterns across all of them at once. But understanding what those patterns actually mean still requires us human readers to ask the right questions.

--
## Works Cited

Underwood, Ted. "The Risks of Distant Reading." *Distant Horizons: Digital Evidence and Literary Change*. University of Chicago Press, 2019, pp. 143–169.

(Almost) READY FOR GRADING.