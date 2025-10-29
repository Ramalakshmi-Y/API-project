# JSON Tree Visualizer

An interactive web application that visualizes JSON data as a hierarchical tree structure with advanced search, highlighting, and navigation features.

![JSON Tree Visualizer](https://img.shields.io/badge/React-18.3.1-blue) ![TypeScript](https://img.shields.io/badge/TypeScript-5.5.3-blue) ![React Flow](https://img.shields.io/badge/React%20Flow-Latest-brightgreen) ![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.4.1-38bdf8)

## Features

### Mandatory Features

- **JSON Input & Parsing**
  - Text area for pasting or typing JSON data
  - Real-time JSON validation with detailed error messages
  - "Visualize Tree" button to generate visualization
  - Sample JSON data included as placeholder

- **Tree Visualization using React Flow**
  - Hierarchical node tree structure
  - Different node types:
    - **Object nodes** (Blue) - Display object keys
    - **Array nodes** (Green) - Display array indices with item count
    - **Primitive nodes** (Orange) - Display key-value pairs for strings, numbers, booleans, and null
  - Connected parent-child nodes with smooth lines
  - Color-coded nodes for easy identification

- **Search Functionality**
  - Search bar supporting JSON path queries
  - Path formats supported:
    - Dot notation: `$.user.address.city`
    - Bracket notation: `items[0].name`
    - Mixed notation: `$.items[0].specs.cpu`
  - Highlights matching nodes with yellow color
  - Auto-pan to center matched nodes
  - Visual feedback: "Match found" or "No match found" messages

- **Interactive Features**
  - Zoom In/Out controls
  - Fit View button to auto-center the entire tree
  - Pan by dragging the canvas
  - Node hover to display path and value
  - Mini-map for easy navigation
  - Background grid for better spatial awareness

### Bonus Features

- **Dark/Light Mode Toggle**
  - Persistent theme selection (saved in localStorage)
  - Smooth theme transitions
  - Theme-aware node colors and UI elements

- **Clear/Reset Functionality**
  - Clear button to empty JSON input
  - Reset button to return to input view

- **Copy JSON Path**
  - Click copy icon on any node to copy its JSON path
  - Visual confirmation with checkmark icon

- **Download Tree as Image**
  - Export visualization as PNG image
  - Preserves current zoom level and theme

## Tech Stack

- **React 18.3.1** - Modern UI library
- **TypeScript 5.5.3** - Type-safe development
- **React Flow** - Interactive node-based visualization
- **Tailwind CSS 3.4.1** - Utility-first styling
- **Vite 5.4.2** - Fast build tool and dev server
- **Lucide React** - Beautiful icon library
- **html-to-image** - Image export functionality

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd json-tree-visualizer
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to:
```
http://localhost:5173
```

## Usage

### Basic Usage

1. **Enter JSON Data**
   - Paste your JSON data in the text area
   - Or click "Load Sample" to use the pre-filled example
   - Click "Visualize Tree" to generate the tree

2. **Navigate the Tree**
   - Use mouse to pan (drag) and zoom (scroll)
   - Use the zoom controls in the top-right
   - Click "Fit View" to see the entire tree

3. **Search for Nodes**
   - Enter a JSON path in the search bar
   - Examples:
     - `$.user.name` - Find the name property in user object
     - `$.items[0]` - Find the first item in items array
     - `$.items[0].specs.cpu` - Find nested properties
   - Press Enter or click Search
   - The matching node will be highlighted and centered

4. **Copy Node Path**
   - Hover over any node
   - Click the copy icon
   - The JSON path is copied to clipboard

5. **Download Visualization**
   - Click the download icon in the top-right
   - The tree will be saved as PNG image

6. **Toggle Theme**
   - Click the sun/moon icon in the header
   - Theme preference is saved automatically

### Example JSON Paths

```json
{
  "user": {
    "name": "John",
    "address": {
      "city": "New York"
    }
  },
  "items": [
    { "id": 1, "name": "Laptop" }
  ]
}
```

Search paths:
- `$.user.name` → Finds "John"
- `$.user.address.city` → Finds "New York"
- `$.items[0].name` → Finds "Laptop"
- `items[0].id` → Finds 1

## Project Structure

```
json-tree-visualizer/
├── src/
│   ├── components/
│   │   ├── CustomNode.tsx        # Custom node component for tree
│   │   ├── JSONInput.tsx         # JSON input and validation
│   │   └── TreeVisualizer.tsx    # Main tree visualization
│   ├── utils/
│   │   ├── jsonParser.ts         # JSON to tree conversion logic
│   │   └── searchUtils.ts        # Path search and matching
│   ├── types/
│   │   └── index.ts              # TypeScript type definitions
│   ├── App.tsx                   # Main application component
│   ├── main.tsx                  # Application entry point
│   └── index.css                 # Global styles
├── public/                       # Static assets
├── index.html                    # HTML template
├── package.json                  # Project dependencies
├── tsconfig.json                 # TypeScript configuration
├── tailwind.config.js            # Tailwind CSS configuration
├── vite.config.ts                # Vite configuration
└── README.md                     # This file
```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint
- `npm run typecheck` - Run TypeScript type checking

## Key Features Breakdown

### Node Types & Colors

| Node Type | Color (Light) | Color (Dark) | Description |
|-----------|---------------|--------------|-------------|
| Object | Blue | Deep Blue | Represents JSON objects |
| Array | Green | Deep Green | Represents JSON arrays with item count |
| Primitive | Orange | Deep Orange | Represents strings, numbers, booleans, null |
| Highlighted | Yellow | Yellow | Search match highlight |

### Search Functionality

The search supports JSONPath-like syntax:
- Root: `$` (optional)
- Dot notation: `.property`
- Bracket notation: `[index]` or `[property]`
- Nested paths: `$.user.address.city`
- Array access: `items[0].name`

### Interactive Controls

- **Zoom In/Out**: Control zoom level
- **Fit View**: Auto-fit entire tree in viewport
- **Pan**: Drag canvas to navigate
- **Mini-map**: Overview of entire tree structure
- **Node Hover**: Display full path and value

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Considerations

- Efficiently handles JSON structures up to several hundred nodes
- Automatic layout optimization for balanced tree structure
- Lazy rendering with React Flow for smooth performance
- Optimized search algorithm for quick path matching

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Future Enhancements

- [ ] Export to JSON Schema
- [ ] Support for multiple file upload
- [ ] Collapsible/expandable nodes
- [ ] Custom color themes
- [ ] JSON editor with live preview
- [ ] Share visualization via URL
- [ ] Support for YAML input

## License

MIT License - feel free to use this project for any purpose.

## Author

Built as part of APIWIZ Frontend Developer Assignment

## Acknowledgments

- React Flow for the excellent visualization library
- Tailwind CSS for rapid UI development
- Lucide React for beautiful icons
- Vite for blazing-fast development experience

---

**Note**: This project was built according to the requirements specified in the APIWIZ Frontend Developer Assignment. All mandatory features and several bonus features have been implemented with attention to code quality, UI/UX design, and maintainability.
