# AI Inference Engineering Handbook - Development Guide

## Project Overview

This is an **interactive educational handbook** built as a single-page React application embedded in [index.html](../index.html). The handbook teaches AI inference engineering concepts from fundamentals to production deployment across 31 topics organized into 7 parts.

**Architecture**: Inline React SPA with no build tooling - the entire application (5000+ lines) lives in one self-contained HTML file with embedded JSX, making it instantly shareable and deployable.

## Content Structure

The handbook follows a progressive learning path:

1. **Part I: Fundamentals** - AI models, weights, activations, inference basics
2. **Part II: Computation Graphs** - Graph structures, static vs dynamic, optimization
3. **Part III: Runtimes** - PyTorch, OpenVINO, TensorRT, ONNX, llama.cpp
4. **Part IV: Hardware** - Kernels, CPU/GPU, ISAs, CUDA, specialized hardware
5. **Part V: Optimization** - Memory management, quantization, KV-cache, batching
6. **Part VI: Deployment** - ASR/LLM deployment, benchmarking, monitoring
7. **Part VII: Advanced** - Hyperparameters, call center optimization, troubleshooting

## Code Patterns & Conventions

### Section Components Pattern

Each section follows a consistent structure:
```jsx
case 'section-id':
  return (
    <div className="space-y-6">
      {/* 1. Title */}
      <h1 className="text-4xl font-bold text-gray-900 mb-4">Topic Title</h1>
      
      {/* 2. Plain Explanation (color-coded by part) */}
      <div className="bg-[color]-50 p-6 rounded-lg border border-[color]-200">
        <h2>Plain Explanation</h2>
        <p>Core concept in accessible language</p>
      </div>
      
      {/* 3. Mental Model */}
      <div className="bg-gradient-to-r from-[color]-100 to-[color]-100 p-6 rounded-lg">
        <h3>💡 Mental Model</h3>
        <p>Memorable analogy or comparison</p>
      </div>
      
      {/* 4. Detailed Content (diagrams, examples, tables) */}
      
      {/* 5. Navigation Button */}
      <button onClick={() => { markComplete('section-id'); setActiveSection('next'); }}>
        ✓ Mark Complete & Continue →
      </button>
    </div>
  );
```

### Color Coding by Part
- **Purple**: Part I (Fundamentals)
- **Yellow**: Part II (Graphs) 
- **Green**: Part III (Runtimes)
- **Red**: Part IV (Hardware)
- **Indigo**: Part V (Optimization)
- **Pink**: Part VI (Deployment)
- **Orange**: Part VII (Advanced)

### Component Patterns

**Visual Diagrams**: Use arrow icons and colored boxes for flow diagrams
```jsx
<div className="flex items-center space-x-4">
  <div className="bg-blue-500 text-white px-6 py-4 rounded-lg">Step 1</div>
  <ChevronRight className="w-6 h-6 text-gray-400" />
  <div className="bg-green-500 text-white px-6 py-4 rounded-lg">Step 2</div>
</div>
```

**Code Examples**: Dark terminal theme with syntax highlighting
```jsx
<div className="bg-gray-900 text-green-400 p-4 rounded-lg text-sm">
  <p className="text-blue-400 mb-2"># Comment</p>
  <pre>{`code here`}</pre>
</div>
```

**Comparison Tables**: Gray header, alternating row colors for readability

**Callout Boxes**: Border-left accent with emoji indicators
- Blue (`border-blue-500`): Key insights (💡)
- Yellow (`border-yellow-500`): Warnings/considerations (⚠️)
- Green (`border-green-500`): Completion markers (✅)

## Content Guidelines

### Technical Accuracy
- Concepts are explained for **IT/platform engineers without ML background**
- Each topic includes concrete examples from ASR (Whisper) and LLM deployments
- Performance numbers and configurations reflect real-world production scenarios
- Hardware specifications and benchmarks should be current (2024-2026 timeframe)

### Writing Style
1. **Plain Explanation**: Start with accessible analogies before technical details
2. **Mental Models**: Provide memorable comparisons (e.g., "OpenVINO = Intel's turbocharger for CPU inference")
3. **Practical Focus**: Always connect concepts to operational implications
4. **Progressive Disclosure**: Build complexity gradually within each topic

### Examples Pattern
When adding examples, provide side-by-side ASR vs LLM comparisons:
```jsx
<div className="grid md:grid-cols-2 gap-6">
  <div className="bg-blue-50 p-6 rounded-lg">
    <h3>🎤 ASR Example</h3>
    {/* Whisper/audio use case */}
  </div>
  <div className="bg-green-50 p-6 rounded-lg">
    <h3>💬 LLM Example</h3>
    {/* Language model use case */}
  </div>
</div>
```

## State Management

The app uses React useState hooks for:
- `activeSection`: Current topic being displayed
- `completedSections`: Set tracking which topics user has finished
- `expandedTopics`: Set controlling sidebar navigation expansion

**Navigation flow**: Completion buttons call `markComplete(section)` and `setActiveSection(next)` to track progress.

## Styling System

**Framework**: TailwindCSS utility classes (CDN-loaded)

**Responsive Design**: Use `md:` breakpoints for desktop layouts that stack on mobile

**Visual Hierarchy**:
- `text-4xl font-bold` for main headings
- `text-2xl font-semibold` for section headings  
- `text-xl font-semibold` for subsection headings
- `text-sm` for body text in cards/tables

## Deployment & Distribution

**Zero build required**: The HTML file can be opened directly in any browser or served via any static hosting (GitHub Pages, S3, Netlify, etc.).

**Dependencies** (all CDN-loaded):
- React 18
- Babel Standalone (JSX transformation)
- TailwindCSS
- Lucide React (icons)

## Modification Workflow

When adding new content:
1. **Add topic to sections array** with unique ID, title, icon, and color
2. **Create case in renderContent()** switch statement following section pattern
3. **Link navigation**: Update previous section's button to point to new section
4. **Maintain color coding**: Use part-appropriate colors throughout
5. **Test completion flow**: Verify markComplete and navigation work correctly

## Key Technical Concepts Covered

**Core Topics**: Model weights vs activations, static/dynamic graphs, quantization (INT8/INT4), VRAM management, kernel fusion, batching strategies

**Frameworks**: PyTorch eager vs TorchScript, OpenVINO IR format, TensorRT engines, ONNX portability, llama.cpp/GGUF

**Hardware**: CPU (x86-64, ARM), GPU (CUDA, ROCm), ISAs (AVX-512, AMX, NEON), specialized accelerators (TPU)

**Production**: Real-time vs batch inference, P95/P99 latency, cost optimization, failure modes, monitoring strategies

## Quality Standards

- **No broken links**: All section navigation must be tested
- **Consistent terminology**: Use "inference runtime" not "inference engine", "weights" not "parameters" when discussing storage
- **Real examples**: Performance numbers should cite specific hardware (A100, Xeon, etc.)
- **Accessibility**: Maintain semantic HTML structure and readable color contrasts
