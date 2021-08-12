# Qiskit Textbook Styleguide

This repository contains a style guide for writing in the Qiskit Textbook. It also includes a [Vale-compatible](https://github.com/errata-ai/vale) implementation of these guidelines. This repository is based on the [Errata-ai/write-good](https://github.com/errata-ai/write-good) template, modified to fit the tone of the Qiskit Textbook and to be more specific to quantum computing.

# How to write for the Qiskit Textbook

## Why you should read this

No one wants to read a writing guide, especially when they’re often long lists of petty nit-picks, or full of obvious things like “check your spelling”. In this guide, I’m not going to tell you how to write (I’ll assume you’re already good at that), and I’ll leave the list of nit-picks as a reference at the end (we should have a linter for this soon too). Instead, I’ll discuss how to make sure your writing is appropriate specifically for the textbook. I’ll explain why I chose certain rules, so you can break them if appropriate, or argue with me to change them. Reading this guide should help you:
 - Keep your chapter consistent with other pages in the textbook
 - Keep writing clear for the intended audiences
 - Make things easier when we come to review

To thank you for reading this, I’ll try to keep it light and concise. 

## Tips on the general direction

### 1. Write something you’re excited about

We already cover most of the quantum algorithms you’d find in a traditional course, and we don’t really get requests for new chapters unless they’re submitted by someone proposing to write it themselves. This means, if you want to write something new for the textbook, it should be a story you are excited to tell. Show us a beautiful proof, an unexpected connection between topics, or just something you learnt recently that got your imagination going. We don’t just want content for the sake of content. If you work out what you’re excited about, then the reader will find it exciting too.

### 2. Be honest with the reader

Writers often worry about making their topic seem important, especially when they're trying to justify their research. Sensationalising quantum algorithms can lead to a pretty disappointing experience when the reader is finally presented with a noisy 5-qubit device, or when they learn that future quantum computers are going to take roughly [a billion](https://youtu.be/H1UdcAdw5kg?t=272) times longer per Boolean operation, rendering a whole category of algorithms unfeasible.

Fortunately, we can solve this problem via (#1); if you’re excited about the topic because it’s interesting, or does something cool, then this should be why the reader is interested, not because it’ll lead to sentient AI or self-driving cars. Be honest; explain heuristic algorithms have no guarantees, explain classical computers are tough competitors, and let them decide for themselves if they want to read on.

### 3. Write for the audience (this is WIP)

Imagine someone (undergrad maybe) comes to your desk. They say “I found this paper on the arXiv on <topic>, but I don’t get it.” This is who we’re writing for. If they can read the arXiv then they don’t need the textbook. (TODO: review this; do we only want people below arXiv-reading, or even lower?).

We trust the reader actually wants to read the page. Keep it conversational.


### 4. Take full advantage of the format

Before we get onto flashy interactive things, print media already comes with a lot of often-overlooked tools:
- Don’t describe things that are better shown as images and vice-versa. If drawing isn’t your strong point, it's ok to do a sketch on paper and take a photo. 
- Use bullet points for lists, don’t try to make it a connected paragraph.
- Use regular headings and subheadings to break up the chapter (see [segmenting principle](https://en.wikipedia.org/wiki/E-learning_(theory)#Empirically_established_principles)).

The Qiskit Textbook isn’t constrained to static text and images. There are already loads of great books on quantum computing. We aren’t trying to compete with these books; we want to enhance them. We have a load of great tools available, here’s a quick run-down of why we’ve selected them for use in the textbook:
- **Code cells** are potentially the most powerful interactive elements in the textbook: 
  - Working code makes it harder to hide things from the reader. If there’s a specific part of an algorithm we glossed over, they can dig into that, and we can’t hide circuits (or other things) as black boxes. Bear this in mind when you write code: Keep the logic clear, add useful comments to your code, try not to use advanced Python features, and (where possible) write simple functions yourself instead of importing.
  - Live code means readers can experiment and explore. If they want to know how the code behaves on different inputs, or what’ll happen if they modify a function, they can try it. Write code examples with this in mind. Try not to hard-code circuits. Sometimes it’s unavoidable, but patterns are easier to spot if the reader can change a variable and see how the code reacts.
  - Code examples are practice for the real world. Write code to the standard you’d expect to see in Qiskit. We’ve recently started using pylint to test some of the code, you can see the pylintrc [here](https://github.com/qiskit-community/platypus/blob/main/notebooks/.pylintrc). 

- **Quizzes** are best used to check the reader hasn’t accidentally got the wrong message. Think of common misconceptions, or guess how your text could be misinterpreted, kind of like error-handling. We want the reader to think either “Great, I understood that correctly, I can continue”, or “Wait, what‽ I must have got the wrong end of the stick.” Don’t use these to pick out random facts listed in the paragraphs above.

- **Tooltips** make the text and equations look friendlier. They can help your writing reach a wider audience by offering extra guidance for those that need it, without annoying those that don’t.
  - Text tooltips are similar to the reminder blocks, but for smaller nuggets of information. You can use text tooltips to keep your text shorter and more focussed by hiding context and definitions. Don’t use them to introduce key concepts, they’re more like reminders, or for bringing people up to speed if they’re not familiar with something. You can also include bits of trivia or interesting observations.
  - Use math tooltips as much as possible, even for things you think should be obvious. Readers can’t google Greek symbols like they can with unfamiliar words. Lots of symbols are often re-used in different contexts, so even mathematically mature readers will benefit from them. If you use the tooltips, you shouldn’t describe variables underneath unless you’re explaining them further (this is better than [splitting attention](https://en.wikipedia.org/wiki/Split_attention_effect) between equations and the sentences underneath).



These tools group bits of content together instead of listing it linearly down the page. Grouping content like this helps break up the page, keeps related concepts together (see [contiguity principle](https://en.wikipedia.org/wiki/E-learning_(theory)#Empirically_established_principles)), and stops visual overload.
- **Tabs** are like bullet points that help keep the page short. Use them for related topics that don’t need to be presented in a specific order. You can add details or interesting facts without convoluting or ruining the flow of the page.
- **Carousels:** Use these to tell a short story, this works best with images. Carousels are especially useful for showing how the same thing evolves through different states; it’s more natural to see the thing change in the same place, rather than multiple instances spread across the page.
- **Reminders** are for digressions. Reminders should contain information that either:
  - The reader should already know, and we’re doing them a favour by reminding them or pointing them to helpful resources (see [expertise effect](https://en.wikipedia.org/wiki/Expertise_reversal_effect)). For this, the heading should be “Reminder”.
  - The reader doesn’t need to know, but might find interesting and gives more context. You can give a more instructive heading here, e.g. “Key experiments in quantum physics”, don’t use “Reminder”.
  - I’m also experimenting with using the details tags in quizzes to give hints, you can try this too if you think you need it.

## Tips for writing

Avoid the passive voice. If you’re not familiar, the passive voice is where you say "The <object> was/is/can be <acted on>" instead of "<actor> <acted on> the <object>". For example, "the qubit is measured" is passive, whereas "Frank measures the qubit" is active. It’s used to avoid mentioning who did the action, but it makes writing bland and difficult to read. You can use "we", or "you" to avoid passive voice (it's actually a good thing, see [personalization principle](https://en.wikipedia.org/wiki/E-learning_(theory)#Empirically_established_principles)). When writing for the textbook, use "we" to mean "the writers" and "you" to mean "the reader", or "one". You should only use the passive voice when using the active voice makes things unclear or more wordy.

There are also some coding practices that I think are particularly useful to writers too:
- **Rewrite and refactor:** You’re unlikely to produce your best writing in one take. Get a first draft down, then check you’re still happy with the structure. Re-arrange, re-write, then focus on smaller details.
- **Use a [duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging):** You’re trying to explain something, but everything you write ends up extremely wordy. Turn to your friend (real or complex) and say “Basically, what I’m trying to say is…”, then write down what comes after. This also helps keep things conversational and personal.
