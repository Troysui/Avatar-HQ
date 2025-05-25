# Avatar-HQ
AvatarHQ is a collection of 200 hand-drawn avatar portraits at 1024 × 1024 resolution, each identity-matched to a real face from CelebA-HQ and accompanied by a rich textual caption stored in `captions.json`; the repository also includes five-fold train/validation splits so the data can be plugged directly into style-transfer, text-to-image, or cross-modal retrieval experiments. After cloning the repo, simply drop the `images/` directory and the caption file into the project root and you can iterate over samples immediately—for example, run

```python
import json, random, pathlib, PIL.Image as Image
root = pathlib.Path('images')
img  = random.choice(list(root.glob('*.png')))
print(json.loads(open('captions.json').read())[img.stem])
Image.open(img).show()


AvatarHQ contains three directories—avatar/ (200 high-resolution hand-drawn portraits, 1024 × 1024 PNG), realistic/ (the identity-matched CelebA-HQ reference photos), and text/ (plain-text files whose names mirror the image IDs and whose contents are concise English descriptions of the corresponding faces). Clone the repository, iterate over paired files by matching the shared filename stem (e.g., 0001.png, 0001.txt), and you can immediately run any avatar-generation, style-transfer, or text-to-image experiment without extra parsing or JSON conversion; a minimal Python example is import pathlib, random, PIL.Image as Image; root=pathlib.Path('avatar'); name=random.choice([p.stem for p in root.glob('*.png')]); print(open(f'text/{name}.txt').read().strip()); Image.open(root/f'{name}.png').show(). The dataset is released under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International licence (CC BY-NC-SA 4.0), restricting use to non-commercial research, while all accompanying code is MIT-licensed; using the data signifies acceptance of the CC terms, and any commercial application requires written permission from the authors. If AvatarHQ helps your work, please cite it as @dataset{avatarhq2025, author={Sui, Linjie and Prasad, Mukesh}, title={AvatarHQ: A High-Quality Hand-Drawn Avatar Dataset}, year={2025}, url={https://github.com/<user>/AvatarHQ}, note={CC BY-NC-SA 4.0}}. Direct questions, issues, or collaboration proposals to Linjie Sui (linjie.sui-1@uts.edu.au) or Mukesh Prasad (mukesh.prasad@uts.edu.au).
