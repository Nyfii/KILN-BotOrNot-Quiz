**Bot or Not** Quiz App is a fullscreen quit app used in workshops. It shows questions (text, images, audio and videos) and gives instant feedback to the responses. It doesn't track score and runs directly in your browser.

## Adding Questions

### File Hierarchy

``` 
BotOrNot/
	- index.html
	- admin.html
	- converter.html
	Questions/
		- questions.js
		- QuestionFile1.ybki
		- QuestionFile2.ybki
		...
	Resources/
		- MediaFile1.*
		- MediaFile2.*
		...
```

All the questions should go in the Questions folder, while MediaFiles like images, videos, audios go in the Resources Folder.

### Adding new Questions file

```YAML
# For Media write the FileName. The File needs to be in the correct location. 
# The following Formats are supported:
# Image: .png, .jpg, .webp
# Video: .mp4
# Audio: .mp3, .wav

# Text + 4 Answers (for 2 Answers have 2 answer Options)
Question: [QUESTION_TEXT_HERE]
Answer: [CORRECT_ANSWER]
Answer: [INCORRECT_ANSWER]
Answer: [INCORRECT_ANSWER]
Answer: [INCORRECT_ANSWER]
Explanation: [EXPLANATION]
Label: [LABEL]

---

# 2 Media + 2 Answers
Media: [CORRECT_MEDIA]
Media: [INCCORECT_MEDIA]
Explanation: [EXPLANATION]
Label: [LABEL]

---

# 1 Media + 2 Answers
Media: [MEDIA]
Answer: [CORRECT_ANSWER]
Answer: [INCORRECT_ANSWER]
Explanation: [EXPLANATION]
Label: [LABEL]
```

Where:

- `Question`: Is the written part of a Questions
- `Answer`: Are the Answer possibilities
- `Media`: Is the Name of a Video, Image or Audio file that should be played
- `Explanation`: Explanation why the Response is correct or incorrect
- `Label`: Is the Label / Category of the Question

`---` is the Question Separator. Single Line Comments can be written with `#` (Only at the beginning of a line). The Questions should be either grouped, by who asked them (if something is unclear this makes it easy asking back), or Question Type.

**Naming Conventions**

Questions should just be named: `[NAME].ybki`. The Media should be labeled `[NAME]_FAKE_[CONTENT].*` or `[NAME]_REAL_[CONTENT].*`

### Converting `.ybki` to the `Questions.js` File

1. Open the `converter.html` in your browser
2. Upload one or more `.ybki` files
3. Click **Parse & Merge** (Check for errors)
4. Download the JS
5. Save the generated `Questions.js` in the `Questions/` folder
6. Refresh the Quiz App.