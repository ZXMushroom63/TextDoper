# TextDoper
Text Doping is an (exploit?) that allows bypassing almost any AI content detector. (As of March 3, 2024)

```
data:text/html,%3Ch2%3EText%20Doper%3C%2Fh2%3E%20%3Cdiv%3E%3Cinput%20type%3D%22range%22%20min%3D0%20max%3D1%20step%3D0.1%20value%3D0.6%20data-zwsp%20oninput%3D%22dope%28%29%22%3E%3Clabel%3EZero%20Width%20Space%20Threshold%3C%2Flabel%3E%3Cbr%3E%3Cinput%20type%3D%22range%22%20min%3D0%20max%3D1%20step%3D0.1%20value%3D0.4%20data-homo%20oninput%3D%22dope%28%29%22%3E%3Clabel%3EHomoglyph%20Threshold%3C%2Flabel%3E%3Cbr%3E%3Cinput%20type%3D%22range%22%20min%3D0%20max%3D1%20step%3D0.1%20value%3D1.0%20data-space%20oninput%3D%22dope%28%29%22%3E%3Clabel%3ESpace%20Threshold%3C%2Flabel%3E%3Cbr%3E%3Ctextarea%20class%3D%22before%22%20oninput%3D%22dope%28%29%22%20placeholder%3D%22AI%20generated%20text%20here...%22%20label%3D%22000%22%3E%3C%2Ftextarea%3E%20%3Ctextarea%20class%3D%22after%22%20readonly%20placeholder%3D%22Output%20text%20here%22%20label%3D%22000%22%3E%3C%2Ftextarea%3E%3Cp%3E%3C%2Fp%3E%3C%2Fdiv%3E%3Cstyle%3E%20textarea%20%7B%20width%3A%2040vw%3B%20resize%3A%20none%3B%20height%3A%20100%25%3B%20%7D%20div%20%7B%20height%3A%2050vh%3B%20%7D%20%3C%2Fstyle%3E%20%3Cscript%3Ewindow.onerror%20%3D%20%28e%29%20%3D%3E%20%7Balert%28e%29%7D%3C%2Fscript%3E%20%3Cscript%3E%20function%20dope%28%29%20%7B%20var%20out%20%3D%20%22%22%3B%20var%20threshold%20%3D%20document.querySelector%28%22%5Bdata-zwsp%5D%22%29.value%3B%20var%20homoglyphThreshold%20%3D%20document.querySelector%28%22%5Bdata-homo%5D%22%29.value%3B%20var%20spaceThreshold%20%3D%20document.querySelector%28%22%5Bdata-space%5D%22%29.value%3B%20var%20dopechars%20%3D%20%5B%22%5Cu200c%22%2C%20%22%5Cu200d%22%2C%20%22%5CuFEFF%22%5D%3B%20var%20dopeCount%20%3D%200%3B%20var%20spacechars%20%3D%20%5B%22%5Cu2008%22%2C%20%22%5Cu2007%22%5D%3B%20var%20arr%20%3D%20document.querySelector%28%22.before%22%29.value.split%28%22%22%29%3B%20arr.forEach%28char%3D%3E%7B%20if%20%28Math.random%28%29%20%3E%20homoglyphThreshold%29%20%7B%20out%20%2B%3D%20char.replace%28%22.%22%2C%20%22%5Cu002e%22%29.replace%28%22K%22%2C%20%22%5Cu212A%22%29.replace%28%22%3A%22%2C%20%22%5Cu2236%22%29.replace%28%22A%22%2C%20%22%5Cu0410%22%29.replace%28%22a%22%2C%20%22%5Cu0430%22%29.replaceAll%28%22M%22%2C%20%22%5Cu041C%22%29.replaceAll%28%22X%22%2C%20%22%5Cu0425%22%29.replaceAll%28%22x%22%2C%20%22%5Cu0445%22%29.replaceAll%28%22E%22%2C%20%22%5Cu0415%22%29.replaceAll%28%22e%22%2C%20%22%5Cu0435%22%29.replaceAll%28%22O%22%2C%20%22%5Cu041E%22%29.replaceAll%28%22o%22%2C%20%22%5Cu043E%22%29%3B%20dopeCount%2B%2B%3B%7D%20else%20if%28Math.random%28%29%20%3E%20spaceThreshold%29%20%7Bout%20%2B%3D%20char.replace%28%22%20%22%2C%20spacechars%5BMath.floor%28Math.random%28%29%20%2A%20spacechars.length%29%5D%29%3B%20dopeCount%2B%2B%3B%7D%20else%20%7B%20out%20%2B%3D%20char%3B%20%7D%20if%20%28Math.random%28%29%20%3E%20threshold%29%20%7B%20out%20%2B%3D%20dopechars%5BMath.floor%28Math.random%28%29%20%2A%20dopechars.length%29%5D%3B%20dopeCount%2B%2B%3B%7D%20%7D%29%3B%20document.querySelector%28%22.after%22%29.value%20%3D%20out%3B%20document.querySelector%28%22p%22%29.innerText%20%3D%20%22Inserted%20%22%2BdopeCount%2B%22%20doping%20characters.%22%3B%7D%20%3C%2Fscript%3E
```
*Copy the above code and paste it into a new tab to open the text doper page*


### How does it work?
AI detectors look for patterns that denote an AI model. 
You may have noticed that putting weird punctuation and misspellings in AI-generated content causes the human probability to increase, all that Text Doper does is take that one step further.
It:
1. Randomly inserts zero-width spaces between characters
2. Randomly replaces eligible letters with their homoglyphs (Latin A from English to Cyrillic A, both look identical but are different chars)
3. Replaces spaces with other space characters of the same width.

### Capabilities (As of March 3, 2024)
Bypass:
- Winston AI
- QuillBot AI Detector
- Scribbr AI detector
- ZeroGPT
- Writer AI Detector
- contentatscale AI detector
- detecting-ai.com
- Copyleaks (triggers unsupported language message)
- Sapling AI

Not Bypass:
- GPTZero
  - But GPTZero detects my human writing as AI, so it doesn't really count.

### Please don't use this for academic misconduct
Just don't, it's lazy
