# 100 Balls Battle Royale — Brainrot Edition

A Python script that generates a **"100 Balls Battle Royale — Brainrot Edition"** video using Pillow, MoviePy, NumPy, gTTS, and pydub. Designed to run in Google Colab.

## Description

100 balls, each representing a popular brainrot meme character, compete in a shrinking arena. Random challenges (fireballs, spinning lasers, lava zones, vortices, meteors, and more) eliminate balls one by one until only one ball remains — the winner.

- 100 unique brainrot characters (Tralalero Tralala, Skibidi Toilet, Giga Chad, Doge, Pepe, and more)
- Randomized challenge selection each run
- Automatic audio generation with gTTS
- Character avatars downloaded from ui-avatars.com with per-character colors
- ~90 second video output at 30 fps

## How to Run (Google Colab)

1. Open [Google Colab](https://colab.research.google.com/)
2. Create a new notebook
3. Paste the entire contents of `CODE` into a single cell
4. Run the cell — dependencies are installed automatically
5. The video file will be saved to `/content/brainrot_battle/` and can be downloaded

## Configuration

Key configuration options are in the `Config` dataclass near the top of the script:

| Option | Default | Description |
|--------|---------|-------------|
| `width` | 720 | Video width in pixels |
| `height` | 1280 | Video height in pixels (9:16 vertical format) |
| `fps` | 30 | Frames per second |
| `duration` | 90.0 | Race duration in seconds |
| `ball_count` | 100 | Number of balls |
| `ball_radius` | 18 | Starting ball radius |
| `seed` | None | Random seed (None = random each run) |
| `output_dir` | `/content/brainrot_battle` | Output directory |

## Character List

The script includes 100+ brainrot characters including:

**Italian Brainrot:** Tralalero Tralala, Bombardino Crocodilo, Tung Tung Sahur, Ballerina Cappuccina, Lirili Larila, Brr Brr Patapim, Chimpanzini Bananini, Boneca Ambalabu, Capuccino Assassino, Frigo Camelo, Trippi Troppi, La Vaca Saturno, Glorbo, Bombombini Gusini, Cocofanto

**Skibidi Toilet:** Skibidi Toilet, Cameraman, Speakerman, TV Man, Titan Cameraman, Plungerman

**Internet Classics:** Sigma Boy, Rizz God, Rizzler, Giga Chad, John Pork, Grimace Shake, Smurf Cat, Ohio Boss, Gyatt King, Hawk Tuah, Kai Cenat, Speed, Caseoh, Fanum Tax, Duke Dennis, Baby Gronk, Quandale Dingle, Amogus, Freddy Fazbear, Doge, Pepe, Nyan Cat, Big Chungus, Ugandan Knuckles, Sans Undertale, Sonic, Creeper, Steve MC, Drip Goku, Shrek, Spongebob, Walter White, Rick Astley, Mr Beast, Hasbulla, Toothless Dance, Pingu, Goofy Ahh, Peter Griffin, Morbius, Thanos, Dababy, Stonks, Bingus, Floppa, and many more.

## Dependencies

- [moviepy](https://pypi.org/project/moviepy/) — Video generation
- [Pillow](https://pypi.org/project/Pillow/) — Image rendering
- [numpy](https://pypi.org/project/numpy/) — Array operations
- [gTTS](https://pypi.org/project/gTTS/) — Text-to-speech audio
- [pydub](https://pypi.org/project/pydub/) — Audio processing
- [requests](https://pypi.org/project/requests/) — Image downloading

All dependencies are installed automatically when running the script.
