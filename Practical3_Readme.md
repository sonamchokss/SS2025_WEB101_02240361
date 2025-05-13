# Practical 3: File Upload Application with Next.js

## Project Overview
A React/Next.js application featuring:
- File uploads with progress tracking
- Drag-and-drop interface
- Client-side validation (file type, size)
- Server-side file handling

## Features
- Drag and drop file uploads
- Real-time upload progress
- File validation (type, size)
- Responsive design
- Error handling

## Setup Instructions

### Prerequisites
- Node.js (v18+)
- npm (v9+)

### Installation
1. Clone the repository:
```bash
git clone
cd file-upload
```

2. Install dependencies:
```bash
npm install
```

3. Environment setup:
- Create .env.local file:
```env
UPLOAD_DIR=public/uploads
MAX_FILE_SIZE=10485760 # 10MB
ALLOWED_TYPES=image/jpeg,image/png,application/pdf
```

4. Run the development server:
```bash
npm run dev
```

5. Open your browser at:
http://localhost:3000

## Project Structure
```
file-upload/
├── pages/
│   ├── api/
│   │   └── upload.js     
│   └── index.js  
├── public/
│   └── uploads/ 
├── components/
│   └── FileDropzone.js 
└── styles/
    └── globals.css 
```

## Key Dependencies
- next.js: React framework
- react-hook-form: Form management
- formidable: Server-side file parsing
- axios: HTTP requests
- react-dropzone: Drag-and-drop functionality

## Usage Guide
1. Upload Files:
- Click to browse or drag files into the dropzone
- Supported types: JPEG, PNG, PDF (max 10MB)

2. Progress Tracking:
- Real-time progress bar during uploads
- Success/error notifications

3. Validation:
- Client-side checks before upload
- Server-side verification

4. View Uploads:
- Files saved to public/uploads
- Accessible at /uploads/filename