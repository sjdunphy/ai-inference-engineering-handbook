# Content Filling Plan for AI Inference Engineering Handbook

**Date:** January 26, 2026  
**Task:** Fill 21 placeholder topics in index-new.html with content from index.html  
**Status:** Topics 19-23 (Part V) do NOT exist in source - skip these

---

## Overview

**Target File:** `index-new.html` (1,334 lines)  
**Source File:** `index.html` (5,241 lines of React JSX)  
**Topics to Fill:** 21 topics (6-18, 24-31)  
**Topics to Skip:** 5 topics (19-23 - not available in source)

---

## Topics List & Status

### ✅ Already Complete (5 topics)
- Introduction
- Topic 1: What Is an AI Model?
- Topic 2: Weights and Parameters
- Topic 3: Activations and Memory
- Topic 4: Training vs Inference

### 🔄 Need to Fill (21 topics)

**Part II: Computation Graphs (Topics 5-7)**
- ✓ Topic 5: Understanding Computation Graphs (lines ~4000-4500 in source)
- ✓ Topic 6: Static vs Dynamic Graphs (lines ~4000-4500 in source)
- ✓ Topic 7: Graph Optimization (lines ~4500-5000 in source)

**Part III: Runtimes & Frameworks (Topics 8-13)**
- ✓ Topic 8: What Is an Inference Runtime? (lines ~2500-3000)
- ✓ Topic 9: PyTorch Runtime (lines ~2500-3000)
- ✓ Topic 10: OpenVINO (lines ~2000-2500)
- ✓ Topic 11: TensorRT (lines ~2500-3000)
- ✓ Topic 12: ONNX Runtime (lines ~3000-3500)
- ✓ Topic 13: llama.cpp and Variants (lines ~3000-3500)

**Part IV: Hardware & Silicon (Topics 14-18)**
- ✓ Topic 14: Kernels and Operations (lines ~4500-5000)
- ✓ Topic 15: CPU vs GPU Architecture (lines ~4500-5241)
- ✓ Topic 16: Instruction Set Architectures (ISA) (lines ~1000-2000)
- ✓ Topic 17: CUDA and Alternatives (lines ~1500-2500)
- ✓ Topic 18: Specialized AI Hardware (lines ~2000-2500)

**Part V: Memory & Optimization (Topics 19-23)**
- ❌ Topic 19: RAM vs VRAM - **DOES NOT EXIST IN SOURCE**
- ❌ Topic 20: Quantization Techniques - **DOES NOT EXIST IN SOURCE**
- ❌ Topic 21: Calibration - **DOES NOT EXIST IN SOURCE**
- ❌ Topic 22: KV-Cache Optimization - **DOES NOT EXIST IN SOURCE**
- ❌ Topic 23: Batching Strategies - **DOES NOT EXIST IN SOURCE**

**Part VI: Production Deployment (Topics 24-27)**
- ✓ Topic 24: ASR Deployment Guide (lines ~500-1000)
- ✓ Topic 25: LLM Deployment Guide (lines ~500-1500)
- ✓ Topic 26: Benchmarking and Metrics (lines ~500-1500)
- ✓ Topic 27: Production Monitoring (verify in Part VII section)

**Part VII: Advanced Topics (Topics 28-31)**
- ✓ Topic 28: Hyperparameter Tuning (lines ~1-500)
- ✓ Topic 29: Call Center ASR Optimization (lines ~1-500)
- ✓ Topic 30: Common Failure Modes (lines ~1-500)
- ✓ Topic 31: Troubleshooting Guide (lines ~1-500)

---

## Placeholder Format in index-new.html

Each placeholder section follows this EXACT format:

```html
        <section class="content-section section-hidden" id="section-TOPIC-ID">
            <h1>X. Topic Title</h1>
            <div class="card card-COLOR">
                <h2>Coming Soon</h2>
                <p>This section is being built. Content will be added shortly.</p>
            </div>
            <button class="btn btn-full" onclick="navigateTo('NEXT-TOPIC'); markComplete('TOPIC-ID');">Continue →</button>
        </section>
```

**Color Mapping by Part:**
- Part I: `card-purple`
- Part II: `card-yellow`
- Part III: `card-green`
- Part IV: `card-red`
- Part V: `card-indigo`
- Part VI: `card-pink`
- Part VII: `card-orange`

---

## JSX to HTML Conversion Rules

### Global Replacements

1. **className → class**
   ```jsx
   className="text-4xl" → class="text-4xl"
   ```

2. **onClick → onclick** (and convert handler)
   ```jsx
   onClick={() => { markComplete('id'); setActiveSection('next'); }}
   →
   onclick="navigateTo('next'); markComplete('id');"
   ```

3. **Remove JSX wrapper**
   ```jsx
   case 'topic-id': return (
     <div>content</div>
   );
   →
   <div>content</div>
   ```

4. **React Icons → Text Symbols**
   ```jsx
   <ChevronRight className="w-6 h-6" /> → →
   <ChevronDown className="w-6 h-6" /> → ↓
   <Check className="w-4 h-4" /> → ✓
   ```

5. **Inline Styles** (rare, but keep if present)
   ```jsx
   style={{width: '200px'}} → style="width: 200px"
   ```

### Code Blocks

**JSX:**
```jsx
<pre className="bg-gray-900 text-green-400 p-4 rounded text-sm">
  {`code here`}
</pre>
```

**HTML:**
```html
<pre class="bg-gray-900 text-green-400 p-4 rounded text-sm">code here</pre>
```

### Tables

Tables convert straightforwardly - just change className to class:
```jsx
<table className="w-full">
  <thead className="bg-gray-100">
    <tr>
      <th className="p-3">Header</th>
    </tr>
  </thead>
</table>
```

---

## Step-by-Step Process

### Step 1: Locate Source Content

For each topic, read the corresponding lines from `index.html`:

**Example for Topic 6 (Static vs Dynamic Graphs):**
```bash
# Search for the topic
grep -n "case 'static-dynamic'" index.html
# Read from that line +/- 500 lines
```

**Line Ranges (approximate):**
- Topics 5-7: Lines 4000-5000
- Topics 8-13: Lines 2000-3500
- Topics 14-15: Lines 4500-5241
- Topics 16-18: Lines 1000-2500
- Topics 24-27: Lines 500-1500
- Topics 28-31: Lines 1-500

### Step 2: Extract Topic Content

Each topic in index.html is wrapped like this:
```jsx
case 'topic-id': return (
  <div className="space-y-6">
    <!-- CONTENT HERE -->
  </div>
);
```

Extract everything INSIDE the return statement, excluding the outer `case` and `return`.

### Step 3: Convert JSX to HTML

Apply all conversion rules from section above:
1. Change all `className` to `class`
2. Convert `onClick` handlers to `onclick="navigateTo('next'); markComplete('id');"`
3. Remove JSX template literals (backticks) from code blocks
4. Replace React icons with text symbols
5. Ensure all quotes are properly formatted

### Step 4: Find Placeholder in index-new.html

Search for the section ID:
```bash
grep -n "section-static-dynamic" index-new.html
```

This gives you the line number of the placeholder.

### Step 5: Replace Placeholder

**Find the EXACT placeholder text:**
```html
        <section class="content-section section-hidden" id="section-static-dynamic">
            <h1>6. Static vs Dynamic Graphs</h1>
            <div class="card card-yellow">
                <h2>Coming Soon</h2>
                <p>This section is being built. Content will be added shortly.</p>
            </div>
            <button class="btn btn-full" onclick="navigateTo('graph-opt'); markComplete('static-dynamic');">Continue →</button>
        </section>
```

**Replace with converted content:**
```html
        <section class="content-section section-hidden" id="section-static-dynamic">
            <h1>6. Static vs Dynamic Graphs</h1>
            <!-- CONVERTED CONTENT GOES HERE -->
            <button class="btn btn-full" onclick="navigateTo('graph-opt'); markComplete('static-dynamic');">Continue →</button>
        </section>
```

**Important:** Keep the button at the end - don't remove it!

---

## Critical Conversion Examples

### Example 1: Mental Model Card

**JSX (from index.html):**
```jsx
<div className="bg-gradient-to-r from-purple-100 to-pink-100 p-6 rounded-lg">
  <h3 className="text-xl font-semibold text-gray-800 mb-3">
    💡 Mental Model
  </h3>
  <p className="text-2xl font-bold text-purple-700 text-center py-4">
    Weights = Model's <span className="underline">knowledge stored as numbers</span>
  </p>
</div>
```

**HTML (for index-new.html):**
```html
<div class="bg-gradient-to-r from-purple-100 to-pink-100 p-6 rounded-lg">
  <h3 class="text-xl font-semibold text-gray-800 mb-3">
    💡 Mental Model
  </h3>
  <p class="text-2xl font-bold text-purple-700 text-center py-4">
    Weights = Model's <span class="underline">knowledge stored as numbers</span>
  </p>
</div>
```

### Example 2: Navigation Button

**JSX:**
```jsx
<button 
  onClick={() => {
    markComplete('weights');
    setActiveSection('activations');
  }}
  className="w-full bg-purple-600 text-white px-6 py-3 rounded-lg hover:bg-purple-700 transition-colors font-semibold"
>
  ✓ Mark Complete & Continue to Activations →
</button>
```

**HTML:**
```html
<button class="btn btn-full" onclick="navigateTo('activations'); markComplete('weights');">
  ✓ Mark Complete & Continue to Activations →
</button>
```

**Note:** The placeholder already has the correct button - just keep it!

### Example 3: Code Block

**JSX:**
```jsx
<pre className="bg-gray-900 text-green-400 p-4 rounded text-sm">
{`import torch

model = WhisperModel()
output = model(audio)`}
</pre>
```

**HTML:**
```html
<pre class="bg-gray-900 text-green-400 p-4 rounded text-sm">import torch

model = WhisperModel()
output = model(audio)</pre>
```

### Example 4: Grid Layout

**JSX:**
```jsx
<div className="grid md:grid-cols-2 gap-6">
  <div className="bg-blue-50 p-6 rounded-lg">
    <h3>Column 1</h3>
  </div>
  <div className="bg-green-50 p-6 rounded-lg">
    <h3>Column 2</h3>
  </div>
</div>
```

**HTML:**
```html
<div class="grid md:grid-cols-2 gap-6">
  <div class="bg-blue-50 p-6 rounded-lg">
    <h3>Column 1</h3>
  </div>
  <div class="bg-green-50 p-6 rounded-lg">
    <h3>Column 2</h3>
  </div>
</div>
```

---

## Recommended Order of Filling

**Priority 1 (Do First):** Part II (Topics 5-7)
- These are the first missing topics after the completed ones
- Good for testing the conversion process
- Smaller sections

**Priority 2:** Part III (Topics 8-13)
- Core runtime content
- 6 topics - substantial but manageable

**Priority 3:** Part IV (Topics 14-18)
- Hardware topics
- Topic 15 is long - be careful

**Priority 4:** Part VII (Topics 28-31)
- Practical guides
- Very detailed sections with lots of code

**Priority 5:** Part VI (Topics 24-27)
- Deployment guides
- May have longer code examples

**Skip:** Part V (Topics 19-23) - Not available in source

---

## Testing After Each Fill

After filling each topic, test:

1. **Navigation:** Click the topic in sidebar, verify it opens
2. **Button:** Click "Continue →" button at bottom, verify next topic opens
3. **Styling:** Check cards, tables, code blocks render correctly
4. **Dark Mode:** Toggle theme button, verify colors work
5. **Progress:** Mark complete checkbox, verify it saves

---

## Common Pitfalls to Avoid

❌ **DON'T:**
- Remove the navigation button at the end
- Change the section ID
- Change the onclick handler format
- Add extra whitespace inconsistently
- Forget to convert className to class
- Keep JSX template literals (backticks)

✅ **DO:**
- Keep exact indentation (8 spaces for section content)
- Maintain the section wrapper structure
- Convert ALL className to class
- Test after each major section
- Verify the button navigates to correct next topic

---

## Validation Checklist

Before considering a topic complete:

- [ ] All `className` converted to `class`
- [ ] All `onClick` converted to `onclick` with correct format
- [ ] Navigation button preserved and working
- [ ] Section ID unchanged
- [ ] No JSX artifacts (backticks, React components)
- [ ] Code blocks properly formatted
- [ ] Tables display correctly
- [ ] Cards have correct color class
- [ ] Emojis and special characters preserved
- [ ] No JavaScript errors in browser console

---

## Topic-Specific Notes

### Topic 11 (TensorRT)
- Has complex code examples
- Multiple pre/code blocks - be careful with formatting

### Topic 15 (CPU vs GPU)
- Very long topic (lines 4500-5241)
- Large comparison tables
- Mental model cards

### Topics 28-31 (Part VII)
- Lots of practical code examples
- Configuration files with special formatting
- Pay attention to indentation in code blocks

### Topic 24-25 (Deployment Guides)
- Step-by-step instructions
- Command-line examples
- Be careful with shell commands

---

## File Locations

**Target File:** `c:\Users\saaju\Documents\Ai Projects\Learning Handbooks\ai-inference-engineering-handbook\index-new.html`

**Source File:** `c:\Users\saaju\Documents\Ai Projects\Learning Handbooks\ai-inference-engineering-handbook\index.html`

---

## Estimated Time

- Per topic: 15-30 minutes (depending on length)
- Total for 21 topics: 5-10 hours
- Recommend: Do 3-5 topics at a time, test thoroughly

---

## Success Criteria

✅ All 21 available topics filled with complete content  
✅ All navigation works correctly  
✅ All styling preserved (cards, tables, code blocks)  
✅ Dark mode works on all new content  
✅ Progress tracking functional  
✅ No broken links or missing sections  
✅ Topics 19-23 remain as placeholders (source not available)

---

## Final Notes

- The source content is high quality - don't modify the educational content
- Focus on accurate JSX→HTML conversion
- Test frequently to catch issues early
- If something doesn't work, compare with completed topics 1-4
- The handbook uses TailwindCSS - all classes should work out of the box

**Good luck! The content is excellent - just needs proper conversion.**
