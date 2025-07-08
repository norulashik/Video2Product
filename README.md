# Video2Product
Video2Product is a video-based object detection tool using YOLOv8 to identify real-world items, estimate their size, and fetch online product listings. It scrapes price, rating, reviews, and descriptions from e-commerce links, exporting everything to a CSV file.

## Product Link
https://colab.research.google.com/drive/1LDebrc5KdWu9FrZA3tDjORTXdKCX9X4k?usp=sharing

##  Features

- Upload any real-world **video** (e.g., home scene, product showcase)
- Automatically detect multiple object types using **YOLOv8**
- Estimate object **height, width, and area in centimeters**
- Crop and store clear object samples (max 10 per class)
- Search for products online via **DuckDuckGo**
- Filter results to show only **e-commerce sites** (e.g., Amazon, Flipkart)
- Extract:
  - Product Title
  - Price (₹, $, etc.)
  - Rating
  - Number of Reviews
  - Short Description
- Save all data to a downloadable **CSV file**

##  Methodology

1. **Video Upload** – User provides a `.mp4` or `.avi` file.
2. **YOLOv8 Detection** – Every few seconds, a frame is analyzed.
3. **Bounding Box Analysis** – Width & height in pixels are converted to centimeters.
4. **Frame Annotation** – Bounding boxes with size labels are drawn.
5. **Web Search** – DuckDuckGo is queried for relevant "buy <object>" links.
6. **Scraping** – E-commerce product details are extracted using BeautifulSoup.
7. **Export** – A structured CSV file is saved with all results.

##  Technologies Used

- **YOLOv8 (Ultralytics)** – Object detection
- **OpenCV** – Frame capture and annotation
- **DuckDuckGo** – Search engine interface (no API key needed)
- **BeautifulSoup** – Product data scraping
- **Google Colab / Python** – Platform/environment
- **Matplotlib** – Display annotated frames
- **Pillow (PIL)** – Object image cropping
- **CSV** – Final output format

##  Output CSV Format

| Object Type | Title | Website Link | Price | Rating | Reviews | Description |
|-------------|-------|---------------|--------|--------|----------|-------------|
| sofa | Recliner Sofa | https://amazon.in/... | ₹15,999 | 4.3/5 | 2345 | Plush fabric sofa ideal for living rooms |
| bottle | Steel Bottle | https://flipkart.com/... | ₹499 | 4.6/5 | 1280 | Stainless steel, BPA-free, 1L |


