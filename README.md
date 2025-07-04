<p align="center">
<picture>
<source media="(prefers-color-scheme: dark)" srcset="./docs/assets/logo-dark.svg">
<img width="128" height="128" src="./docs/assets/logo-light.svg">
</picture>
</p>

<h1 align="center">ZoomingOnline</h1>


ZoomingOnline is a web-based data visualization supporting the efficient and scalable Zarr format.

<!-- TODO: make new one once ui stabilizes -->
![demo](./docs/assets/demo.gif)

🌐 Try it live: [https://gosiakk5.github.io/ZoomingOnline/](https://gosiakk5.github.io/ZoomingOnline/)

## 🎯 Aim of the Project

The aim of **ZoomingOnline** is to provide a high-performance web viewer for interactively exploring massive,
gigabyte-scale time-series datasets directly in a browser.

Key features include:

- **Instant Overview:** Utilizes pre-computed data pyramids within the Zarr format to load an initial overview of the
  entire dataset almost instantly.
- **Efficient Zooming:** Fetches only the required high-resolution data chunks for the selected region, with a
  memory-efficient cache to prevent redundant downloads during interaction.
- **Time-Based Controls:** Features a three-level inset zoom interface with draggable windows and sliders that snap to
  meaningful time units (e.g., 10 µs, 100 ns) for precise analysis.
- **Data Toolkit:** Includes a suite of CLI scripts for generating test data, converting from HDF5, and managing cloud
  storage.

## 🛠 Available CLI Scripts

| Script                    | Description                                      |
|---------------------------|--------------------------------------------------|
| `generate_data.py`        | Generate .zarr or .h5 oscilloscope-like datasets |
| `convert_hdf5_to_zarr.py` | Convert HDF5 files to Zarr format                |
| `data_to_s3_importer.py`  | Recursively convert + upload to S3 bucket        |
| `cors_server.py`          | Serve .zarr files locally with CORS enabled HTTP |

📖 See [scripts.md](./docs/scripts.md) for detailed CLI usage and arguments.

## 🚀 Quick Start

1. Clone the repository
2. Follow [setup.md](./docs/setup.md) to install dependencies and configure
3. Create or serve a Zarr dataset:
   <!-- Check: Run -->
   ```bash
   python src/generate_data.py -o waveform.zarr
   ```
   ```bash
   python src/cors_server.py
   ```
4. View in browser: http://localhost:8000/website, website/index.html or on online
   at [https://gosiakk5.github.io/ZoomingOnline/](https://gosiakk5.github.io/ZoomingOnline/)
5. In the input field enter http://localhost:8000/waveform.zarr or any other Zarr URL

## 📄 License

MIT License — see [LICENSE](LICENSE)