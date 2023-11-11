# ElevenLabs

---

# **Introduction**

> The AI has been trained on a vast amount of audiobooks, and to a lesser extent, podcasts. This is the context it understands the best, and it provides the most predictable results when generating voiceovers. If you write something in the style of a book, the AI can sometimes interpret how to perform a certain passage from the context of the writing itself. To achieve a more emotive vocal range, you can lower the stability slider, although this may sacrifice some degree of predictability.

# **Emotion**

> If you want the AI to express a specific emotion, the best approach is to write in a style similar to that of a book. To find good prompts to use, you can flip through some books and identify words and phrases that convey the desired emotion. For instance, you can use dialogue tags to express emotions, such as “he said, confused”, or “he shouted angrily”. These types of prompts will help the AI understand the desired emotional tone and generate a voiceover that accurately reflects it. With this approach, you can create highly customized voiceovers that are perfect for a variety of applications.

```
"Are you sure about that?" he said, confused.
"Don’t test me!" he shouted angrily.
```

# **Pacing**

> Based on my own testing, which contradicts some information out there, I believe that when you use multiple samples in a clone, the AI puts them back-to-back without any space between them. This can lead to pacing issues and cause the AI to talk faster than it should. This is likely why some people have reported fast-talking clones. To control the pacing of the speaker, you can use the same approach as in emotion, where you write in a style similar to that of a book. While it's not a perfect solution, it can help improve the pacing and ensure that the AI generates a voiceover at the right speed. With this technique, you can create high-quality voiceovers that are both customized and easy to listen to.

```
"I wish you were right, I truly do, but you're not," he said slowly.
```

# **Pause**

> Personally, the one trick I use the most to control when to pause and to get longer pauses is a simple dash (-) or the em-dash (—).

```
"It - is - getting late."
```

> Ellipsis (…) also work to add a pause between words but usually, for me at least, also adds some "hesitation" or "nervousness" to the voice that might not always fit.

```
""I... yeah, I guess so...""
```

> The system is always being improved upon, and ElevenLabs are currently working on adding features such as the ability to add pauses and change the speed of the generated voiceovers. Currently, you can add a pause by using the MLSS tag <break time="3000" />, where the number is the length of the pause in milliseconds (1000ms = 1s). This will insert a pause of the specified duration into the generated voiceover. Alternatively, you can achieve a pause by inserting a line break or two where you want the pause to occur. The AI will often recognize the change in the text and adapt accordingly, resulting in a natural-sounding pause. With these techniques, you can customize your voiceovers even further and create highly polished content that meets your specific needs.

```
Welcome

to this guided meditation.

Find a comfortable seated position, 

with your back straight and your feet on the ground.
```

---
