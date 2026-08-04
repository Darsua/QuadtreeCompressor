# Quadtree-Based Image Compression

A C++ implementation of image compression using the Quadtree algorithm and the Divide and Conquer paradigm. Images are partitioned recursively into quadrants, preserving detail in complex regions and averaging out uniform ones to reduce file size.

---

## Features

- Compress images using quadtree decomposition
- Multiple error metrics to control compression quality:
  - Variance
  - Mean Absolute Deviation (MAD)
  - Max Pixel Difference (MPD)
  - Entropy
- Adjustable compression threshold and minimum block size
- Target compression ratio mode (automatic threshold search)
- ASCII splash screen

---

## How It Works

The program divides an image into 4 quadrants recursively. If a block is "simple enough" (below the error threshold), it is replaced with the average color of that block. Complex blocks are split further. The result is a compressed image where uniform regions are coarsely approximated and detailed regions retain more fidelity.

---

## Requirements

- Windows
- `stb_image.h` and `stb_image_write.h` in the working directory

---

## Usage

Run the pre-built binary:
```
bin/Quad.exe
```

The program prompts interactively:
```
Enter the path to your image:
> input.png

1. Variance
2. Mean Absolute Deviation
3. Max Pixel Difference
4. Entropy
Enter the method of compression (1 to 4):
> 1

Enter the threshold value (e.g., 63):
> 50

Enter the minimum block size (e.g., 15):
> 10

Enter the target compression ratio (e.g., 0.5). Enter 0 to ignore:
> 0.6

Enter the output path for the processed image:
> output.png
```

---

## Input / Output

- Supports standard image formats (PNG, JPG) via `stb_image`
- Input path is entered interactively
- Output is saved as PNG

---

## Output Metrics

After compression, the program reports:

| Metric | Description |
| :--- | :--- |
| Size before / after | File sizes in bytes |
| Compression ratio | Ratio of output to input size |
| Tree depth | Maximum depth of the quadtree |
| Total nodes | Number of nodes in the quadtree |

---

## Author

Darrel Adinarya Sunanda `13523061` — [@Darsua](https://github.com/Darsua)

---

## License

MIT
