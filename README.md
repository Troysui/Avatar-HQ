Avatar-HQ
=========

AvatarHQ is a lightweight dataset organised into three folders:

* **avatar/** – 200 hand-drawn portraits (PNG, 1024 × 1024)  
* **realistic/** – the identity-matched CelebA-HQ reference photos  
* **text/** – plain-text captions; each file shares its stem with the corresponding images (`0001.txt`, `0001.png`, …)

Clone the repository and you can iterate over paired samples straight away—no JSON parsing needed.  
A one-liner demonstration:

```python
import pathlib, random, PIL.Image as Image
root = pathlib.Path('avatar')
name = random.choice([p.stem for p in root.glob('*.png')])
print(open(f'text/{name}.txt').read().strip())
Image.open(root / f'{name}.png').show()
