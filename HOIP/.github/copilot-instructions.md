# Méridia District Energy Dashboard - AI Agent Instructions

## Project Overview
This is a static web application visualizing energy data for ParcMéridia district, featuring three main views:
- **Block Dashboard** (`parcmeridia_energy_dashboard.html`): Detailed hourly PV vs demand charts for individual blocks
- **District Digital Twin** (`src/index.html`): 3D Three.js visualization of buildings with interactive selection
- **Environmental Portal** (`src/simulation.html`): Gateway to external Autodesk Forma simulation

## Architecture & Data Flow
- **Data Structure**: 18 blocks with hourly energy data (PV generation, residential/office/retail demand) for summer/winter seasons
- **Aggregation**: Block data aggregates to district totals in the 3D view
- **State Management**: Seasonal switching affects all visualizations
- **File Organization**: Root HTML files for standalone views, `src/` for interconnected components

## Key Patterns & Conventions

### Styling
- **Theme**: Dark background (#060812) with cyan/blue accents (#38bdf8)
- **Fonts**: Inter for UI text, DM Mono for data/metrics
- **Colors**: 
  - PV: #4ade80 (green)
  - Residential: #38bdf8 (cyan)
  - Office: #a78bfa (purple)
  - Retail: #f59e0b (amber)
- **Components**: Glassmorphism panels with backdrop blur and subtle borders

### Data Visualization
- **Chart.js**: Line charts with tension: 0.4, no point radius, custom tooltips
- **Three.js**: BoxGeometry buildings scaled by kWp, emissive highlighting on selection
- **Formatting**: kWh/MWh/GWh with smart scaling, percentage self-sufficiency

### Code Structure
- **Seasonal Data**: `block.summer`/`block.winter` arrays with 24 hourly entries
- **Interactive Selection**: Raycasting for 3D building clicks, DOM updates for popups
- **Data Processing**: Reduce operations for district aggregation

## Development Workflow
- **Server**: Live Server on port 5501 (configured in .vscode/settings.json)
- **Libraries**: All via CDN (Chart.js, Three.js, Tailwind CSS)
- **No Build Process**: Direct HTML/JS editing
- **Testing**: Open in browser, test seasonal switching and interactions

## Common Tasks
- **Adding Blocks**: Extend BLOCKS array with consistent data structure
- **New Metrics**: Add to data objects and update chart datasets
- **Styling**: Use Tailwind classes with custom CSS variables for theming
- **3D Features**: Import from three/addons/, position relative to camera controls

## External Dependencies
- Chart.js 4.4.1 for all charting
- Three.js 0.152.2 with OrbitControls for 3D
- Tailwind CSS via CDN
- Autodesk Forma for environmental simulation (external link)

## File Reference Examples
- Block data structure: `parcmeridia_energy_dashboard.html` lines 325-330
- 3D scene setup: `src/index.html` lines 180-200
- Chart configuration: `src/index.html` lines 140-160
- Styling patterns: Any file's `<style>` sections</content>
<parameter name="filePath">/Users/cheesecakke/Desktop/HOIP/.github/copilot-instructions.md