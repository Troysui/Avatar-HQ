# Avatar-HQ
AvatarHQ is a collection of 200 hand-drawn avatar portraits at 1024 × 1024 resolution, each identity-matched to a real face from CelebA-HQ and accompanied by a rich textual caption stored in `captions.json`; the repository also includes five-fold train/validation splits so the data can be plugged directly into style-transfer, text-to-image, or cross-modal retrieval experiments. After cloning the repo, simply drop the `images/` directory and the caption file into the project root and you can iterate over samples immediately—for example, run

```python
import json, random, pathlib, PIL.Image as Image
root = pathlib.Path('images')
img  = random.choice(list(root.glob('*.png')))
print(json.loads(open('captions.json').read())[img.stem])
Image.open(img).show()
