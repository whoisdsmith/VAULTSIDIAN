---
PromptInfo:
 promptId: artAnime
 name: 🖼️ Generate a anime photo 
 description: select a text and photo with the style of anime will be generated using Dalle-2
 author: Prompt Engineering Guide
 tags: photo, dalle-2,art
 version: 0.0.1
config:
 append:
  bodyParams: false
  reqParams: true
 context: "prompt"
 output: '`\n![](${requestResults.data[0].url})`'
bodyParams:
 n: 1
 size: "1024x1024"
reqParams:
 url: "https://api.openai.com/v1/images/generations"
---

# Artanime

{{selection}}, anime

---

#AI #imageprompts