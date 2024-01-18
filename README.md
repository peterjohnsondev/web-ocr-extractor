# Get Text - OCR Image to Text Extractor

<div align="center">

  [![Next.js](https://img.shields.io/badge/Next.js-13.5-black?style=flat-square&logo=nextdotjs)](https://nextjs.org/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
  [![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3-38B2AC?style=flat-square&logo=tailwindcss)](https://tailwindcss.com/)
  [![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

</div>

## 📖 Overview

**Get Text** is a modern web application that extracts text from images using advanced Optical Character Recognition (OCR) technology. Built with Next.js and powered by Tesseract.js, it provides a fast, intuitive interface for converting images to editable text. Perfect for digitizing documents, scanning receipts, or extracting text from screenshots.

## ✨ Features

- 🖼️ **Drag & Drop Interface** - Easily upload images by dragging or clicking
- 🚀 **Fast Processing** - Real-time OCR with Tesseract.js
- 📱 **Responsive Design** - Works seamlessly on desktop, tablet, and mobile
- 🎯 **Accurate Text Extraction** - Powered by industry-leading OCR technology
- 🌐 **Browser-Based** - No server required, runs entirely in your browser
- 💅 **Modern UI** - Clean, professional interface built with Tailwind CSS

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Next.js 13** | React framework for production |
| **TypeScript** | Type-safe JavaScript development |
| **Tailwind CSS** | Utility-first CSS framework |
| **Tesseract.js** | Client-side OCR engine |
| **React Hot Toast** | Toast notifications |
| **React Icons** | Icon library |

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 16.x or higher - [Download](https://nodejs.org/)
- **Bun** 1.x or higher (optional) - [Download](https://bun.sh/)
- A modern web browser

## 🚀 Getting Started

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/peterjohnsondev/web-ocr-extractor.git
   cd web-ocr-extractor
   ```

2. **Install dependencies**
   ```bash
   # Using npm
   npm install

   # Or using bun
   bun install
   ```

3. **Run the development server**
   ```bash
   # Using npm
   npm run dev

   # Or using bun
   bun run dev
   ```

4. **Open your browser**
   - Navigate to [http://localhost:3000](http://localhost:3000)
   - The application will hot-reload as you make changes

### Build for Production

```bash
# Using npm
npm run build
npm run start

# Or using bun
bun run build
bun run start
```

## 💡 Usage

1. **Upload an Image**
   - Click the upload area or drag & drop an image file
   - Supported formats: PNG, JPG, JPEG, GIF, WebP

2. **Wait for Processing**
   - The OCR engine processes the image in your browser
   - Watch the progress indicator

3. **Extract Text**
   - Extracted text appears in real-time
   - Copy the text or process additional images

## 📁 Project Structure

```
web-ocr-extractor/
├── src/
│   ├── app/
│   │   ├── layout.tsx          # Root layout configuration
│   │   ├── page.tsx            # Main page component
│   │   └── globals.css         # Global styles
│   ├── components/
│   │   ├── Cards/
│   │   │   └── TextCard.tsx    # Text result card component
│   │   └── Navigations/
│   │       ├── Header.tsx      # Header component
│   │       └── Footer.tsx      # Footer component
│   └── lib/
│       └── convertor.ts        # OCR conversion logic
├── public/                      # Static assets
├── package.json                 # Project dependencies
├── tsconfig.json               # TypeScript configuration
├── tailwind.config.ts          # Tailwind CSS configuration
└── next.config.js              # Next.js configuration
```

## 🔧 Available Scripts

```bash
# Development
npm run dev              # Start dev server with hot-reload

# Production
npm run build            # Build optimized production bundle
npm run start            # Start production server

# Code Quality
npm run lint             # Run ESLint
```

## 🌐 How It Works

The application uses **Tesseract.js**, a JavaScript port of the popular Tesseract OCR engine. Here's the process:

1. User uploads an image file
2. Image is converted to a data URL
3. Tesseract worker processes the image
4. Extracted text is returned and displayed
5. Worker is terminated to free resources

### Key Implementation

The OCR conversion is handled by the `convertor` function in [src/lib/convertor.ts](src/lib/convertor.ts):

```typescript
const convertor = async (img: string) => {
  const worker = await createWorker("eng");
  const ret = await worker.recognize(img);
  const text = ret.data.text;
  await worker.terminate();
  return text;
};
```

## 📊 Performance

- **Processing Speed**: ~2-10 seconds depending on image complexity
- **Browser Memory**: Efficient memory management with worker cleanup
- **Batch Processing**: Extract text from multiple images sequentially

## 🔐 Privacy

- ✅ All processing happens **locally in your browser**
- ✅ **No data** is sent to external servers
- ✅ **No tracking** or analytics
- ✅ Your images remain **private**

## 🚧 Roadmap

- [ ] Support for multiple languages
- [ ] Batch processing for multiple images
- [ ] Export results to PDF/DOCX
- [ ] Advanced image preprocessing options
- [ ] Dark mode toggle
- [ ] History of extracted texts

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🔗 Resources & References

- [Tesseract.js Documentation](https://github.com/naptha/tesseract.js)
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)

## 📧 Support

If you have any questions or encounter issues:

1. Check existing [GitHub Issues](https://github.com/peterjohnsondev/web-ocr-extractor/issues)
2. Create a new issue with detailed information
3. Include screenshots or error messages

## 👨‍💻 Author

**Your Name** - [GitHub Profile](https://github.com/peterjohnsondev)
