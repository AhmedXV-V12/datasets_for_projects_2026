# datasets_for_projects_2026
``` it's dataset for my projects in 2026 ```
you have : 
[bigdb.json](bigdb.json)
[big_data.txt](bigd_data.txt)

in *Text_file*:
```
this is example for text
______________________

this is example2 for text

```

in *json_file*:
```
[
 {
 "content": "this is example for text"
 },
 {
 "content": "this is example2 for text"
 }
]
```

the python file for make the ```txt file``` to ```json file``` :
```
import json

INPUT_FILE = "big_data.txt"
OUTPUT_FILE = "bigdb.json"
SEPARATOR = "______________________"

data_blocks = []
current_block = []

with open(INPUT_FILE, "r", encoding="utf-8") as f:
    for line in f:
        stripped = line.rstrip("\n")

        if stripped == SEPARATOR:
            if current_block:
                text = "\n".join(current_block).strip()
                data_blocks.append({"content": text})
                current_block = []
        else:
            current_block.append(stripped)

if current_block:
    text = "\n".join(current_block).strip()
    data_blocks.append({"content": text})

with open(OUTPUT_FILE, "w", encoding="utf-8") as f:
    json.dump(data_blocks, f, ensure_ascii=False, indent=2)
```

*_By Student:Ahmed Walid Abdalhafeez_*
