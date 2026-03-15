---
title: "Response 1: On the Importance of Context for Visual Communication"
date: 2026-02-22T15:34:30-04:00
categories:
  - blog
tags:
  - response
  - Harry Potter
  - Fan Fics
  - JK Rowling
  - Distant Reading
  - Voyant Tools
  - LLM
  - context
---

<style>
.llm-output { font-size: 0.875em; }
.llm-output h3 { font-size: 1.05em; font-weight: 600; margin: 0.6em 0 0.25em 0; }
.llm-output h4 { font-size: 0.95em; font-weight: 600; margin: 0.5em 0 0.2em 0; }
</style>

## Introduction

In “The Risks of Distant Reading,” Ted Underwood argues that distant reading tools only become meaningful when the person using them brings context to the analysis. These tools can find patterns in text, but without knowing where the data comes from, those patterns might not mean much. For this assignment, I revisit the visualizations I created earlier from a corpus of Harry Potter fan fiction using Voyant Tools and R. I then give these visuals to the LLM Mistral Le Chat with no context and ask it to explain and interpret them. The goal is to see whether the model can produce useful insights from the visuals alone, or whether context is still necessary to understand what the data actually shows.


## 1. Word cloud (no context)

For the first illustration I use the word cloud from Figure 1 of my Assignment 1 post.

<figure>
  <img src="../../assets/images/fig6_word_cloud.png" alt="Voyant Word Cloud — Harry Potter and fan fiction word cloud.">
  <figcaption>Figure 1: Voyant Word Cloud — Harry Potter and fan fiction word cloud.</figcaption>
</figure>

**Prompt:**

```
Please explain and interpret this word cloud.
```

<div class="llm-output" markdown="1">

> **Mistral's response**
>
> 
> This word cloud visually represents the most frequently used words in the *Harry Potter* series, specifically focusing on the first book, *Harry Potter and the Philosopher's Stone* (or *Sorcerer's Stone* in the U.S.). Here’s a detailed interpretation:
>
>### **Key Themes and Characters**
>- **"Harry"**: The largest and most prominent word, indicating that Harry Potter is the central character of the story.
>- **"Hermione" and "Ron"**: These names are also prominent, reflecting the importance of Harry’s two best friends, Hermione Granger and Ron Weasley, in the narrative.
>- **"Voldemort"**: The main antagonist, Lord Voldemort, is highlighted, showing his significance as the primary villain.
>- **"Dumbledore"**: Albus Dumbledore, the wise and powerful headmaster of Hogwarts, is another key figure in the story.
>
>### **Common Words Reflecting Plot and Themes**
>- **"Wand"**: A crucial object in the wizarding world, symbolizing magic and power.
>- **"Magic"**: Central to the story, emphasizing the magical world Harry enters.
>- **"Know" and "Thought"**: These words suggest the themes of discovery, learning, and understanding that are prevalent in the book.
>- **"Looked" and "Eyes"**: These words indicate the importance of observation and perception in the story.
>
>### **Emotional and Action-Oriented Words**
>- **"Turned," "Saw," "Came," "Got"**: These action verbs reflect the dynamic and eventful nature of the plot.
>- **"Dark"**: Likely refers to the darker elements of the story, including the threat posed by Voldemort and the mysterious events at Hogwarts.
>- **"Hand," "Door," "Room"**: These words suggest physical interactions and settings within the story, such as exploring Hogwarts and its secrets.
>
>### **Dialogue and Interaction**
>- **"Said," "Asked," "Told"**: These words indicate the importance of dialogue and communication among characters.
>- **"Just," "Really," "Oh"**: Common in dialogue, these words add a conversational tone to the narrative.
>
>### **Summary**
>The word cloud effectively captures the essence of *Harry Potter and the Philosopher's Stone*: a story about a young boy discovering his identity, forming friendships, and confronting evil in a magical world. The prominence of character names and magical terms highlights the book's focus on adventure, friendship, and the battle between good and evil.

</div>

The LLM was able to identify what kind of books we are dealing with because of the famous names and themes that are present in the word cloud. It also seems to have a good understanding of the plot and the characters, as well as the dialogue and interaction between the characters. But it was only able to say that it included words from the first book in the series but could not work with the idea of fan fictions being involved. It might be because of the abdence/lack of fan fiction from its training data.

## 2. Food heatmap
For the second illustration I will use the food heatmap from Figure 2 of my Assignment 1 post. I will ask mistral in a separate chat to explain and interpret this heatmap with the following prompt:

```
Please explain and interpret this image.
```

In this output the LLM regurgitated the information that was already present in the image and did not provide any new insights. It said that it was a visualization of the frequency of food-related words across different texts or contexts. It extracted the frequency counts from the heatmap and put them into a table at the end of the response.

<table>
  <thead>
    <tr>
      <th>Word</th>
      <th>Sorcerer’s Stone</th>
      <th>Deathly Hallows</th>
      <th>HP Meets HP</th>
      <th>NYU AU</th>
      <th>Djinn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>food</td>
      <td>10</td>
      <td>21</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <td>dinner</td>
      <td>8</td>
      <td>15</td>
      <td>0</td>
      <td>0</td>
      <td>11</td>
    </tr>
    <tr>
      <td>chocolate</td>
      <td>16</td>
      <td>2</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <td>cake</td>
      <td>7</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <td>hungry</td>
      <td>6</td>
      <td>7</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>butterbeer</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>6</td>
    </tr>
    <tr>
      <td>coffee</td>
      <td>1</td>
      <td>3</td>
      <td>0</td>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <td>beans</td>
      <td>6</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>feast</td>
      <td>7</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <td>pudding</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
    </tr>
  </tbody>
</table>


Now, I will ask Mistral to explain and interpret this heatmap with a bit of additional context. I will tell it what texts we are dealing with and try to see what analysis it comes up with. For this round I gave it the following prompt:

```
Please explain and interpret this image. You are given a heatmap of the frequency of food-related words across five Harry Potter texts: *Sorcerer's Stone*, *Deathly Hallows*, which are original texts by JK Rowling, then *HP Meets HP*, *And I Will Find You*, and *Djinn Awakened*, which are fan fictions by CaelynAilene, lyingleia, and Wishmaster1983 respectively.
```
This was the output:

<div class="llm-output" markdown="1">

> This heatmap visualizes the frequency of food-related words across five Harry Potter texts: two original works by J.K. Rowling (*Sorcerer's Stone* and *Deathly Hallows*) and three fanfictions (*HP Meets HP*, *And I Will Find You* (NYU AU), and *Djinn Awakened*). Here’s a detailed interpretation:
>
>### **Structure of the Heatmap**
>- **Rows:** Food-related words (e.g., "food," "dinner," "chocolate," etc.).
>- **Columns:** Titles of the five texts.
>- **Color Intensity:** Represents the frequency of each word in the corresponding text. Darker colors indicate higher frequency.
>
>### **Key Observations**
>
>#### **1. Sorcerer’s Stone (Original Text)**
>- **"Chocolate"** is the most frequent word (16 times), likely reflecting its iconic role in the story (e.g., the scene where Harry receives chocolate from Ron on the Hogwarts Express).
>- **"Food"** (10), **"dinner"** (8), and **"feast"** (7) are also prominent, emphasizing the importance of communal meals and celebrations in the narrative.
>- **"Beans"** (6) and **"hungry"** (6) appear moderately, possibly referencing the characters' experiences with food scarcity or treats like Bertie Bott’s Every Flavour Beans.
>
>#### **2. Deathly Hallows (Original Text)**
>- **"Food"** (21) and **"dinner"** (15) dominate, suggesting a focus on meals, possibly tied to the characters' journeys and moments of respite during the war.
>- **"Cake"** (9) and **"butterbeer"** (4) are notable, indicating celebratory or comforting food items.
>- **"Chocolate"** (2) appears less frequently compared to *Sorcerer’s Stone*, perhaps reflecting a shift in tone or context.
>
>#### **3. HP Meets HP (Fanfiction)**
>- None of the listed food-related words appear in this text, suggesting that food is not a central theme or that the narrative focuses on other elements.
>
>#### **4. And I Will Find You (NYU AU) (Fanfiction)**
>- Only **"chocolate"** (1) and **"coffee"** (1) appear, indicating minimal emphasis on food-related words. This could reflect a modern or alternate universe setting where food is less central to the plot.
>
>#### **5. Djinn Awakened (Fanfiction)**
>- **"Dinner"** (11) and **"food"** (5) are the most frequent words, showing a focus on meals, possibly in a domestic or social context.
>- **"Butterbeer"** (6) and **"coffee"** (5) are also prominent, suggesting a blend of magical and mundane food/drink items.
>- **"Pudding"** (3) and **"cake"** (2) appear occasionally, indicating the presence of desserts or treats in the narrative.
>
>### **Interpretation and Themes**
>
>#### **Original Texts vs. Fanfictions**
>- **Original Texts (*Sorcerer’s Stone* and *Deathly Hallows*):**
>  Food-related words are frequent, reflecting the importance of meals, treats, and communal dining in the Harry Potter universe. These words often tie into key moments of comfort, celebration, or character development (e.g., chocolate as a remedy for Dementor exposure, feasts in the Great Hall).
>
>- **Fanfictions (*HP Meets HP*, *And I Will Find You*, *Djinn Awakened*):**
>  Food-related words are less frequent or absent, suggesting that these stories may focus on different themes or settings. For example:
>  - *HP Meets HP* does not mention food at all, possibly indicating a plot-driven or dialogue-heavy narrative.
>  - *And I Will Find You* (NYU AU) includes minimal food references, which may reflect its modern or alternate universe setting.
>  - *Djinn Awakened* includes some food-related words, particularly "dinner" and "butterbeer," suggesting a blend of magical and everyday life.

>### **Conclusion**
>The heatmap highlights how food-related words are used differently across original texts and fanfictions. In the original works, food plays a significant role in world-building and character experiences, while fanfictions vary widely—some ignore food entirely, and others incorporate it in unique ways. This reflects the diverse creative directions taken by fanfiction authors compared to J.K. Rowling’s original narratives.

</div>

In this version it is doing a bit more than just regurgitating the information that was already present in the image. It is able to identify the texts that are being dealt with and the frequency of the food-related words in each text. It is also able to identify the original texts and the fanfictions and how they differ in their use of food-related words. It is also able to identify the themes and the patterns in the use of food-related words across the texts.

## 3. What This Experiment Shows About Context

One thing that becomes clear from this experiment is that visuals do not really speak for themselves. Even though visualizations are supposed to summarize data in a clear way, they still need context in order to be interpreted properly. When I first gave the word cloud to Mistral without any context, it immediately assumed that the words came from the first Harry Potter book. This shows that the model relied on recognizable names like Harry, Hermione, and Voldemort to guess what the dataset was. While this guess was partly correct in identifying the franchise, it missed an important part of the dataset: the fact that the corpus also included fan fiction.

The food heatmap shows this issue even more clearly. Without context, the model mostly repeated the information that was already present in the visualization. It described the structure of the heatmap and listed the frequency counts but did not provide much interpretation beyond that. In other words, the visualization alone did not give the model enough information to understand what the texts were or why the differences between them might matter.

However, when I added context explaining that some of the texts were original novels by J.K. Rowling and others were fan fictions, the interpretation became more meaningful. The model was then able to compare the original texts with the fan fiction and suggest that the different frequencies of food-related words might reflect different themes or narrative priorities. Even though the model was still working with the same numbers, the added context allowed it to produce a much more useful interpretation.

This reflects the point that Underwood makes in “The Risks of Distant Reading.” Distant reading tools are very good at identifying patterns in large datasets, but those patterns do not explain themselves. Someone still needs to understand the dataset, the research question, and the broader context of the texts in order to make meaningful interpretations.

## Conclusion

This small experiment shows that visualizations and computational tools do not automatically produce meaningful insights. While the LLM was able to describe the visuals and identify some patterns, its interpretations were limited when it did not have context about the dataset. Once additional information about the texts was provided, the analysis became more useful and more relevant to the corpus. This suggests that visualizations are most effective when they are accompanied by clear explanations and contextual information. Even when using powerful tools like LLMs or distant reading methods, interpretation still depends on understanding the data and the questions being asked.