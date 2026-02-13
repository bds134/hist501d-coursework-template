# Using pip Instead of conda for "OCR with Google Vision and Tesseract"

This guide helps you follow the Programming Historian lesson using pip and virtual environments, rather than conda.

## 1. Upgrade pip (Optional but recommended)

```bash
python -m pip install --upgrade pip
```

## 2. Install Required Packages

Install Tesseract’s Python wrapper and Google Cloud Vision client:

```bash
pip install pytesseract google-cloud-vision pillow
```

NB: 'pillow' is a dependency for image processing, which is required by pytesseract.

## 3. Install Tesseract-OCR Engine

- **Windows:** Download and install from [UB Mannheim builds](https://github.com/UB-Mannheim/tesseract/wiki).
- **Mac:** `brew install tesseract`
- **Linux:** `sudo apt-get install tesseract-ocr`

**Windows users:** You may need to add the Tesseract installation folder (e.g., `C:\Program Files\Tesseract-OCR`) to your system PATH so Python can find it. To do this:

1. Open the Start menu and search for "Environment Variables".
2. Click "Edit the system environment variables" > "Environment Variables".
3. Under "System variables", find and select "Path", then click "Edit".
4. Click "New" and add the path to your Tesseract installation folder (e.g., `C:\Program Files\Tesseract-OCR`).
5. Click OK to save and restart your terminal.

**Mac/Linux users:** If you installed Tesseract with Homebrew or your package manager, it should already be in your PATH. If you get errors, check your installation or consult your package manager's documentation.

## 4. ImageMagick

If you use Tesseract, you will need to convert PDFs to images. ImageMagick is a common tool for this:

- **Windows:** Download and install from [ImageMagick downloads](https://imagemagick.org/script/download.php).
- **Mac:** `brew install imagemagick`
- **Linux:** `sudo apt-get install imagemagick`
- **Windows users:** During installation, make sure to check the option to add ImageMagick to your system PATH.
- **Mac/Linux users:** If you installed ImageMagick with Homebrew or your package manager, it should already be in your PATH. If you get errors, check your installation or consult your package manager's documentation.

Once you have ImageMagick installed, check the version in bash:

```bash
magick -version
```

To convert a multi-page PDF to an image with 300 DPI, use:

```bash
magick -density 300 input.pdf ./PATH/TO/YOUR/OUTPUT/DIR/output-%d.tiff
```

## 5. Set Up Google Cloud Vision

Follow the lesson’s instructions to create a Google Cloud project and download your credentials JSON file. Set the environment variable:

- On Windows (Command Prompt):
  ```cmd
  set GOOGLE_APPLICATION_CREDENTIALS=path\to\your\credentials.json
  ```
- On Windows (PowerShell):
  ```powershell
  $env:GOOGLE_APPLICATION_CREDENTIALS="path\to\your\credentials.json"
  ```
- On Mac/Linux:
  ```bash
  export GOOGLE_APPLICATION_CREDENTIALS=path/to/your/credentials.json
  ```

## 5. Continue with the Lesson

You can now follow the rest of the lesson as written, using your pip environment.

---

For more details, see the [Programming Historian lesson](https://programminghistorian.org/en/lessons/ocr-with-google-vision-and-tesseract).
