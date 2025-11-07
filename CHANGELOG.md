# Changelog - Virtual Tour UNU Yogyakarta

## 🎨 UI Refinement v4.6 (7 November 2025)

### ✨ Modern Loading Screen & Button Consistency

#### 🔘 PMB Button Update

**Rounded Corners Improvement:**
- **Before**: `border-radius: 8px` (sharp rounded corners)
- **After**: `border-radius: 9999px` (pill shape - fully rounded)
- **Purpose**: Match the "EXPLORE THE CAMPUS" button style for visual consistency

**Visual Comparison:**
```
Before:  ┌──────────┐
         │ PMB UNU  │
         └──────────┘

After:   ╭──────────╮
         │ PMB UNU  │
         ╰──────────╯
```

#### ⏳ Loading Screen Redesign

**Previous Design (v4.5 and earlier):**
- Simple blue background (`bg-unu-primary`)
- Basic spinner with white/gold colors
- University icon (🏛️)
- Minimal text layout
- Plain appearance

**New Modern Design (v4.6):**

**1. Gradient Background**
```css
bg-gradient-to-br from-unu-dark via-unu-primary to-black opacity-95
```
- Sophisticated multi-color gradient
- Deep navy → Blue → Black transition
- 95% opacity for depth

**2. Enhanced Spinner Design**
- Outer ring: 96px × 96px (larger for better visibility)
- Border: 4px with white/10 base and gold accent on top
- **Inner icon**: VR Cardboard icon (fa-vr-cardboard) in gold - **SAME as Panorama 360° feature**
- Combined spinner + icon creates professional look with thematic consistency

**3. Typography Matching Landing Page**
- Heading: 
  - Font: Poppins
  - Weight: 300 (light, elegant)
  - Size: 3xl on desktop, 4xl responsive
  - Letter spacing: 0.02em
- Subtext:
  - Color: white/70 (subtle)
  - Letter spacing: 0.1em (wide tracking)
  - Uppercase for emphasis

**4. Animated Progress Dots**
- Three gold dots with pulsing animation
- Staggered animation delay (0s, 0.2s, 0.4s)
- Visual feedback for ongoing loading

**Layout Structure:**
```
┌─────────────────────────────────────┐
│  Gradient Background (Dark→Blue→Black) │
│                                     │
│           ⟳  [Spinner]              │
│           🥽  [VR Icon]             │
│                                     │
│     Memuat Virtual Tour             │
│   MOHON TUNGGU SEBENTAR             │
│                                     │
│          • • •                      │
│     (Animated Dots)                 │
└─────────────────────────────────────┘
```

#### 📊 Component Breakdown

**Loading Screen Elements:**

| Element | Style | Purpose |
|---------|-------|---------|
| Background | Gradient overlay | Modern, depth |
| Spinner | 24px ring, gold top | Loading indicator |
| Icon | **VR Cardboard (gold)** | **Thematic consistency with Panorama 360°** |
| Title | Poppins 300, 3xl | Clear message |
| Subtitle | Uppercase, tracked | Visual hierarchy |
| Dots | Pulse animation | Active feedback |

**Icon Consistency:**
- ✅ **Features Section**: fa-vr-cardboard (Panorama 360°)
- ✅ **Loading Screen**: fa-vr-cardboard (same icon)
- 🎯 **Result**: Visual continuity throughout the experience

**Consistency Achieved:**
- ✅ Same font weights as landing page (Poppins 300)
- ✅ Same letter spacing style (0.02em, 0.1em)
- ✅ Same color palette (unu-dark, unu-gold)
- ✅ Same gradient approach (multi-stop)
- ✅ Same icon style (Font Awesome)
- ✅ **Same VR icon as Panorama 360° feature**

#### 🎯 Design Philosophy

**Why These Changes?**

1. **Button Consistency**: PMB button now matches EXPLORE button shape → unified design language
2. **Loading Screen Sync**: Loading UI now reflects landing page aesthetic → seamless experience
3. **Icon Consistency**: VR Cardboard icon used in both Features and Loading → thematic coherence
4. **Professional Polish**: Gradient + icon + typography → enterprise-level quality
5. **User Experience**: Better visual feedback with animated elements

**Before vs After Summary:**

| Aspect | v4.5 | v4.6 |
|--------|------|------|
| PMB Button | Rounded 8px | Pill shape (9999px) |
| Loading BG | Solid blue | Gradient (dark→blue→black) |
| Spinner | Simple ring | Ring + Icon combo |
| Loading Icon | 🏛️ University | 🥽 **VR Cardboard** |
| Typography | Basic | Poppins 300 (elegant) |
| Animation | Spin only | Spin + Pulse dots |
| Style Sync | Partial | Full landing page match |
| Icon Theme | Generic | **Panorama 360° themed** |

#### 📝 Technical Details

**Files Modified:**
- `frontend/index.html` (v4.6)

**CSS Changes:**
```css
/* PMB Button */
border-radius: 8px → border-radius: 9999px;

/* Loading Screen */
- Simple bg-unu-primary
+ Gradient overlay with absolute positioning
+ VR Cardboard icon (fa-vr-cardboard) - matches Panorama 360°
+ Poppins 300 typography
+ Animated progress dots
```

**Icon Change:**
```html
<!-- Before -->
<i class="fas fa-university text-unu-gold text-3xl"></i>

<!-- After -->
<i class="fas fa-vr-cardboard text-unu-gold text-3xl"></i>
```

**Cache Busting:**
- app.js version: v4.5 → v4.6

---

## 🎨 Logo Update v4.5 (7 November 2025)

### ✨ Dual Logo & Simplified Badge

#### 🏛️ Logo Changes

**1. Dual Logo Side by Side**
- ✅ Added `member-logo-gold.png` next to UNU logo
- ✅ Both logos displayed horizontally with gap
- ✅ Flex layout: `flex items-center justify-center gap-4 md:gap-6`

**Logo Sizes (Larger):**
- **Desktop (>1024px)**: h-28 (112px) - was h-20 (80px)
- **Tablet (768-1024px)**: h-24 (96px) - was h-20 (80px)
- **Mobile (<768px)**: h-16 (64px) - was h-14 (56px)
- **Small (<480px)**: h-14 (56px) - was h-12 (48px)

**Gap Between Logos:**
- Desktop/Tablet: 1.5rem (24px)
- Mobile: 1rem (16px)

**2. 360° Badge Simplified**
- ❌ **Removed**: Background box (rgba blur)
- ❌ **Removed**: Border (1px solid)
- ❌ **Removed**: Padding & border-radius
- ❌ **Removed**: `.tour-badge` class
- ✅ **New**: Plain text only
- ✅ **Style**: 
  - Font: text-sm
  - Weight: font-light
  - Letter spacing: 0.2em (very wide)
  - Class: `tracking-widest`

#### 📐 Visual Layout

**Before:**
```
┌──────────────────────┐
│                      │
│     🏛️ UNU Logo      │
│                      │
└──────────────────────┘
```

**After:**
```
┌────────────────────────────────┐
│                                │
│   🏛️ UNU    📋 Member          │
│   (Bigger)  (Bigger)           │
│                                │
└────────────────────────────────┘
```

**Badge Before:**
```
┌─────────────────────┐
│ 360° VIRTUAL TOUR   │  ← Box with border
└─────────────────────┘
```

**Badge After:**
```
360° VIRTUAL TOUR  ← Text only, no box
```

#### 🎨 CSS Changes

**Removed CSS:**
```css
.tour-badge {
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    padding: 0.5rem 1.25rem;
    border-radius: 4px;
}
```

**New Inline Style:**
```html
<span class="text-sm tracking-widest font-light" 
      style="letter-spacing: 0.2em;">
    360° VIRTUAL TOUR
</span>
```

#### 📱 Responsive Behavior

**Logo Container:**
- Desktop: `gap-6` (24px between logos)
- Mobile: `gap-4` (16px between logos)
- Both logos scale together

**Logo Heights:**
| Screen Size | Logo Size | Member Size |
|-------------|-----------|-------------|
| Desktop (>1024px) | h-28 (112px) | h-28 (112px) |
| Tablet (768-1024px) | h-24 (96px) | h-24 (96px) |
| Mobile (<768px) | h-16 (64px) | h-16 (64px) |
| Small (<480px) | h-14 (56px) | h-14 (56px) |

**Badge Text:**
- All screens: text-sm (0.875rem)
- Letter spacing: 0.2em (extra wide)
- Font weight: 300 (light)

#### 🎯 Design Rationale

**Why Dual Logo:**
- Show organizational membership/partnership
- Balanced visual weight
- Professional credential display

**Why Remove Badge Box:**
- Cleaner, more minimal
- Less visual clutter
- Focus on typography
- Modern aesthetic

**Why Bigger Logos:**
- Better visibility
- Stronger branding
- More prominent identity
- Balanced with member logo

#### 📦 Files Required
- `gold-unu.png` (existing)
- `member-logo-gold.png` (NEW - must be added to frontend folder)

#### ✅ Implementation Checklist
- [x] Add flex container for dual logos
- [x] Increase logo sizes (h-20 → h-28)
- [x] Add member-logo-gold.png reference
- [x] Remove .tour-badge styles
- [x] Convert badge to plain text
- [x] Update responsive sizes
- [x] Add gap between logos
- [x] Test on mobile/tablet/desktop

### 📦 Files Updated
- `index.html` - Dual logo layout + badge simplification
- `CHANGELOG.md` - This documentation

### 🔄 Cache Version
- App.js version: **v4.5**

### 🎨 Visual Comparison

| Element | v4.4 | v4.5 |
|---------|------|------|
| Logo Count | 1 (UNU) | 2 (UNU + Member) |
| Logo Size | h-20 (80px) | h-28 (112px) |
| Logo Layout | Centered | Flex side-by-side |
| Badge Style | Box with border | Text only |
| Badge Background | rgba blur | None |
| Letter Spacing | 2px | 0.2em (wider) |

---

## 🎨 HSHus Layout v4.4 (7 November 2025)

### ✨ Simple & Elegant Hero Design

Redesign hero section untuk match persis dengan layout HSHus - clean, minimalist, dan elegan.

#### 🎯 Layout Changes

**Hero Content Structure (Top to Bottom):**
1. **Logo** (kecil, di atas)
   - Size: h-16 (mobile) / h-20 (desktop)
   - Opacity: 90%
   - Margin bottom: mb-6 (compact)
   
2. **Tagline** (besar, sebagai headline utama)
   - Text: "A vision for zero carbon living and mobility."
   - Style: Font weight 300 (light/thin)
   - Size: 3xl → 5xl → 6xl (responsive)
   - Letter spacing: 0.02em (sedikit lebar)
   
3. **360° Badge** (minimal, rectangular)
   - Background: rgba blur subtle
   - Border: 1px solid white 30%
   - Border radius: 4px (sharp corner, not pill)
   - Padding: 0.5rem 1.25rem
   - Letter spacing: 2px (wide)
   - Font size: 0.875rem
   
4. **EXPLORE Button** (tetap sama)
   - Gold gradient
   - Rounded pill
   - Text: "EXPLORE THE HOME"

#### 🎨 Visual Refinements

**Removed:**
- ❌ University name "Universitas Nahdlatul Ulama Yogyakarta"
- ❌ Tagline as paragraph (sekarang jadi headline)
- ❌ Large logo (diganti dengan small logo)

**Updated:**
- ✅ Logo lebih kecil dan subtle (h-16/h-20 vs h-32/h-40)
- ✅ Tagline jadi main headline dengan font thin
- ✅ Badge rectangular (bukan pill) dengan border sharp
- ✅ Overlay lebih gelap (75%-60%-75% vs 70%-50%-70%)
- ✅ Content positioning lebih centered (-5vh vs -8vh)

#### 📐 Typography Hierarchy

**Desktop:**
```
Logo:    h-20 (80px)
Tagline: text-6xl (3.75rem) font-weight 300
Badge:   text-sm tracking-wider
Button:  text-sm tracking-wide
```

**Mobile (<768px):**
```
Logo:    h-14 (56px)
Tagline: 1.75rem font-weight 300
Badge:   0.7rem letter-spacing 1.5px
Button:  text-sm
```

**Small Mobile (<480px):**
```
Logo:    h-12 (48px)
Tagline: 1.5rem
```

#### 🎭 Style Philosophy

**HSHus Approach:**
- Minimalist dan clean
- Logo sebagai identifier kecil, bukan focal point
- Tagline/vision sebagai hero utama
- Typography thin/light untuk elegance
- Rectangular badge (modern, sharp)
- Dark overlay untuk drama

**Before (UNU Focus):**
- Logo besar sebagai focal point
- University name prominent
- Tagline sebagai supporting text
- Badge rounded/pill
- Emphasis pada branding

**After (Vision Focus):**
- Logo kecil, subtle
- Vision statement sebagai focal
- Clean, minimal, elegant
- Badge sharp/modern
- Emphasis pada message

#### 🎨 Color & Contrast

**Overlay:**
- Top: rgba(0,0,0,0.75) - lebih gelap
- Center: rgba(0,0,0,0.6)
- Bottom: rgba(0,0,0,0.75) - lebih gelap
- Effect: Better contrast untuk white text

**Badge:**
- Background: rgba(255,255,255,0.15)
- Border: rgba(255,255,255,0.3)
- Backdrop blur: 10px
- Style: Glassmorphism subtle

#### 📱 Responsive Behavior

**Logo Sizing:**
- Desktop (>1024px): h-20 (80px)
- Tablet (768-1024px): h-20 (80px)
- Mobile (<768px): h-14 (56px)
- Small (<480px): h-12 (48px)

**Tagline Sizing:**
- Desktop: text-6xl (60px)
- Tablet: text-5xl (48px)
- Mobile: 1.75rem (28px)
- Small: 1.5rem (24px)

**Content Position:**
- Desktop: -5vh (slight up)
- Tablet: -3vh
- Mobile: -2vh
- Effect: More centered feel

### 📦 Files Updated
- `index.html` - Hero layout redesign
- `CHANGELOG.md` - This documentation

### 🔄 Cache Version
- App.js version: **v4.4**

### 🎯 Comparison

| Element | Before | After |
|---------|--------|-------|
| Logo Size | h-32/h-40 | h-16/h-20 |
| Main Text | University Name | Vision Statement |
| Text Weight | Bold (700) | Light (300) |
| Badge Shape | Pill (50px) | Rectangle (4px) |
| Overlay | 70-50-70% | 75-60-75% |
| Letter Spacing | Normal | Wide (0.02em) |
| Content Y | -8vh | -5vh |

---

## 🐛 Critical Bug Fix v4.3 (7 November 2025)

### 🔧 Edge Visibility Prevention

#### Issue
Saat gambar di-geser (pan) atau di-zoom out, muncul bagian abu-abu/kosong (edge) seperti screenshot yang dilampirkan.

#### Root Cause
- Zoom out range terlalu rendah (0.8x) membuat gambar lebih kecil dari viewport
- Pan range terlalu besar saat zoom level rendah
- Tidak ada pembatasan dinamis antara zoom level dan pan range

#### Solution Implemented

**1. Zoom Range Adjustment**
- **Before**: 0.8x - 2.0x (terlalu rendah minimum)
- **After**: 1.0x - 2.0x (prevent zoom out below original size)
- Initial: 1.15x (slight zoom untuk avoid edge)

**2. Dynamic Pan Limits**
- Pan range sekarang **dinamis** berdasarkan zoom level
- Formula: 
  ```javascript
  maxPanX = Math.max(0, (currentScale - 1.0) * 150)
  maxPanY = Math.max(0, (currentScale - 1.0) * 100)
  ```
- **Zoom 1.0x**: Pan disabled (maxPan = 0)
- **Zoom 1.5x**: Pan ±75px horizontal, ±50px vertical
- **Zoom 2.0x**: Pan ±150px horizontal, ±100px vertical

**3. Auto-Adjustment on Zoom**
- Saat zoom berubah, pan position otomatis di-adjust dalam bounds
- Function `adjustPanLimits()` dipanggil saat wheel zoom
- Prevent pan position tetap di luar bounds saat zoom out

**4. Performance Optimization**
- Added `will-change: transform` untuk GPU acceleration
- Smooth constraint enforcement

#### Technical Details

**CSS Changes:**
```css
.hero-bg {
    will-change: transform;
    transform: translateY(50px) scale(1.15); /* min scale 1.15 */
}
```

**JavaScript Logic:**
```javascript
// Prevent zoom out below 1.0
currentScale = Math.min(Math.max(currentScale, 1.0), 2.0);

// Dynamic pan based on zoom
const maxPanX = Math.max(0, (currentScale - 1.0) * 150);
const maxPanY = Math.max(0, (currentScale - 1.0) * 100);
```

#### Result
- ✅ **No edge visibility**: Gambar selalu memenuhi viewport
- ✅ **Smooth constraints**: Pan disabled saat zoom minimum
- ✅ **Natural feel**: Pan range meningkat seiring zoom level
- ✅ **All devices**: Works pada desktop, tablet, mobile

#### Testing Checklist
- [ ] Zoom out minimum 1.0x (tidak bisa lebih kecil)
- [ ] Tidak ada abu-abu/edge saat zoom minimum
- [ ] Pan disabled/minimal saat zoom 1.0x
- [ ] Pan range bertambah saat zoom in
- [ ] Pinch zoom di mobile tetap constrained
- [ ] Smooth pan saat zoom level tinggi

### 📦 Files Updated
- `index.html` - Zoom/pan constraints logic
- `CHANGELOG.md` - This documentation

### 🔄 Cache Version
- App.js version: **v4.3**

---

## 🐛 Bug Fix v4.2 (7 November 2025)

### 🔧 Critical Fixes

#### 1. Background Auto-Zoom REMOVED
- ❌ **Removed**: Auto zoom in/out animation (20s cycle)
- ✅ **New**: Background sekarang **static/diam**
- ✅ **Manual Only**: Zoom/pan hanya dengan mouse/trackpad
- 📐 **Initial State**: `translateY(50px) scale(1.15)`
- 📍 **Position**: `center bottom` (lebih ke bawah)

#### 2. Navbar REMOVED - Fixed Logo & Button
- ❌ **Removed**: Full navbar bar
- ✅ **Logo**: Fixed top-left corner
  - Position: `fixed top-1.5rem left-1.5rem`
  - Sizes: h-12 (mobile) / h-14 (tablet) / h-16 (desktop)
  - Click: → `https://unu-jogja.ac.id`
  - Hover: scale(1.05)
- ✅ **PMB Button**: Fixed top-right corner
  - Style: **Outline** (border gold, transparent)
  - Hover: **Filled** (background gold)
  - Click: → `https://pmb.unu-jogja.ac.id`
  - **No Icon**
  - Size: 0.875rem, padding 0.5rem 1.5rem

#### 3. Layout Adjustments
- ✅ **Background**: Lebih ke bawah (translateY +50px)
- ✅ **Content**: Lebih ke atas
  - Desktop: margin-top -8vh
  - Tablet: margin-top -5vh
  - Mobile: margin-top -3vh
- ✅ **EXPLORE Button**: Smaller size
  - Padding: 0.75rem 2rem (was 1rem 2.5rem)
  - Font: 0.95rem (was text-lg)
  - **No Icon** (removed play-circle)

#### 4. Full Responsive Design
- ✅ **Breakpoints**: 480px, 768px, 1024px
- ✅ **Mobile (<768px)**:
  - Logo: h-12
  - PMB Button: 0.75rem, 0.4rem 1rem padding
  - Title: 2rem
  - Tagline: 1rem
  - CTA: 0.85rem, 0.6rem 1.5rem padding
- ✅ **Small Mobile (<480px)**:
  - Title: 1.5rem
  - Hero Logo: 5rem
- ✅ **Touch Gestures**: Pinch zoom support

### 🎮 Enhanced Interactions

#### Manual Zoom
- Range: **0.8x - 2x** (expanded from 1x-2x)
- Increment: **0.05** (smoother, was 0.1)
- Method: Mouse wheel / trackpad scroll
- Initial: **1.15x** (slight zoom in)

#### Manual Pan
- Range: **Dynamic** based on zoom
  - Formula: `±200 * currentScale`
  - At 1x zoom: ±200px
  - At 2x zoom: ±400px
- Method: Click drag / trackpad swipe / touch swipe
- Initial Y: **50px** (offset bawah)

#### Pinch Zoom (Mobile)
- Two-finger pinch to zoom
- Range: 0.8x - 2x
- Works simultaneously with pan

### 📦 Files Updated
- `index.html` - Complete revision
- `BUGFIX_v4.2.md` - Detailed documentation
- `CHANGELOG.md` - This file

### 🔄 Cache Version
- App.js version: **v4.2**

---

## 🎮 Interactive Hero v4.1 (7 November 2025)

### ✨ NEW: Interactive Background Control

#### 🖱️ Mouse/Trackpad Interaction
- **Zoom with Wheel**: Scroll untuk zoom in/out (1x - 2x)
- **Pan with Drag**: Klik dan drag untuk geser background (±200px range)
- **Trackpad Support**: Swipe 2 jari untuk pan, scroll untuk zoom
- **Smart Detection**: Button dan link tidak terganggu saat drag
- **Cursor Feedback**: `grab` → `grabbing` visual indicator

#### 📱 Touch Support
- **Mobile Pan**: Swipe untuk geser background
- **Touch Gestures**: Native pinch-to-zoom browser support
- **Smooth Transitions**: Transform 0.1s ease-out

#### 🎯 Navbar Simplification
- **Logo Only**: Hanya logo UNU (tanpa text title)
- **Clickable Logo**: Redirect ke `https://unu-jogja.ac.id`
- **Logo Hover**: Scale(1.05) smooth effect
- **PSB UNU Button**: Gold gradient pill button
  - Icon: `fas fa-user-graduate`
  - Redirect: `https://pmb.unu-jogja.ac.id`
  - Style: Sama dengan "EXPLORE THE HOME" (rounded 50px)
  - Hover: Shadow boost + translateY(-2px)

#### 🎨 Technical Implementation
- **Background Size**: 120% untuk allow pan space
- **Position**: top -10%, left -10%
- **Pan Range**: Limited -200px to +200px
- **Zoom Range**: Limited 1x to 2x
- **Performance**: GPU-accelerated transforms
- **Event Handling**: 
  - `wheel` for zoom
  - `mousedown`/`mousemove`/`mouseup` for pan
  - `touchstart`/`touchmove` for mobile

#### ⚡ Performance Optimizations
- Passive event listeners untuk scroll
- Transform-only animations (no reflow)
- Range limits untuk prevent edge visibility
- Debounced updates

### 🔄 Files Updated
- `index.html` - Hero interaction + navbar redesign
- `INTERACTIVE_HERO_GUIDE.md` - Complete documentation
- `CHANGELOG.md` - This file

### 📦 Cache Version
- App.js version: **v4.1**

---

## 🎨 HSHus-Style Design v4.0 (6 November 2025)

### ✨ Complete UI/UX Redesign

Implementasi desain baru mengikuti style HSHus dengan fokus pada simplicity dan best practices.

#### 🖼️ Hero Section
- **Background**: `bg-hero-wide.webp` dengan zoom in/out animation (20s cycle)
- **Animation**: Smooth scale transform (1.0 → 1.1)
- **Overlay**: Dark gradient untuk text readability (70% → 50% → 70%)
- **Logo**: `gold-unu.png` dengan drop shadow glow effect
- **Typography**: 
  - University name: 4xl → 5xl → 6xl responsive
  - Tagline: "A vision for zero carbon living and mobility"
- **Badge**: "360° VIRTUAL TOUR" dengan glassmorphism effect
- **CTA Button**: Gold gradient pill button dengan hover glow

#### 🎯 Navbar
- **Background**: Pure black (rgba(0,0,0,0.95)) dengan backdrop blur
- **Text**: White color untuk semua teks
- **Logo**: Gold UNU logo dengan glow effect
- **Border**: Subtle gold accent line
- **Fixed**: Sticky positioning tetap di atas saat scroll

#### ✨ Features Section
- **Design**: Simple centered cards tanpa heavy shadows
- **Icons**: Gold gradient circles
- **Content**: Focused dan concise descriptions
- **Layout**: 3 columns responsive

#### 📸 Gallery Section
- **Background**: Light gray (gray-50)
- **Header**: Simple dan clean
- **Grid**: Responsive 2-3-4 columns

#### 📱 Footer
- **Background**: Pure black
- **Layout**: 3 columns (About, Links, Social)
- **Logo**: Gold UNU logo
- **Links**: Gold hover effect
- **Social**: Icon buttons dengan hover scale

### 🎨 Design System

#### Colors
```css
Primary Blue: #1e3a8a
Gold Accent: #d4af37
Dark: #0f172a
Black: #000000
White: #ffffff
```

#### Typography
- **Headings**: Poppins (400-800)
- **Body**: Inter (300-700)

#### Animations
- Hero zoom: 20s ease-in-out infinite
- GPU-accelerated transforms
- Smooth transitions (0.3s ease)

### ⚡ Best Practices

#### Performance
- CSS animations (GPU-accelerated)
- WebP image format
- Minimal JavaScript untuk animasi
- Single animation loop

#### Accessibility
- WCAG AA color contrast
- Semantic HTML5
- Alt texts untuk images
- Focus states

#### Responsive
- Mobile-first approach
- Breakpoints: 640px, 768px, 1024px
- Fluid typography
- Touch-friendly (44x44px minimum)

### 📦 Files Updated
- `index.html` - Complete redesign
- `HSHUS_DESIGN_NOTES.md` - Design documentation
- `CHANGELOG.md` - This file

### 🔄 Cache Version
- App.js version: v4.0

---

## 🌟 Major Update v3.0 (6 November 2025) - Landing Page Redesign

### ✨ NEW: Premium Landing Page Implementation

#### 🎨 Hero Section Redesign
- **Animated Dark Background**: Gradient gelap profesional (#0f172a → #1e293b → #334155)
- **Moving Pattern**: Geometric gold pattern dengan animasi translate (30s cycle)
- **Zoom Effect**: Background radial gradient dengan scale + rotate animation (20s cycle)
- **Overlay Gradient**: Multi-layer untuk text readability optimal
- **Floating Logo**: Logo UNU gold ukuran besar (h-40/h-48) dengan:
  - Drop shadow glow effect (rgba gold 0.4)
  - Float animation naik-turun (6s cycle)
- **University Name**: "Universitas Nahdlatul Ulama Yogyakarta" (white, bold, 3xl-4xl)
- **Gold Animated Tagline**: "Berfokus pada Masa Depan, Berkomitmen pada Keberlanjutan"
  - Gradient text dengan color shift animation
  - Background size 200% dengan position animation
- **Badge Glassmorphism**: "360° VIRTUAL TOUR" dengan backdrop blur
- **Premium CTA Button**: 
  - Gold gradient background (#d4af37 → #f0c674)
  - Shadow dengan gold glow
  - Hover: translateY + shadow boost
  - Icon compass + "Mulai Jelajahi Kampus"
- **Scroll Indicator**: Chevron bounce animation

#### 🎯 Features Section Enhanced
- **Section Header**: Title dengan gold accent
- **3 Feature Cards**:
  - VR Card: Blue gradient icon (#1e3a8a → #1d4ed8)
  - Map Card: Gold gradient icon (#d4af37 → #eab308)
  - Info Card: Green gradient icon (#16a34a → #10b981)
- **Card Effects**: 
  - White background dengan border subtle
  - Rounded corners (xl)
  - Shadow lg → xl on hover
  - TranslateY lift effect (-8px)
  - Icon dalam rounded square dengan gradient

#### 📸 Gallery Section Improved
- **Enhanced Header**: 
  - Title dengan gold text accent
  - Subtitle instructions
  - Mouse pointer icon indicator
- **Responsive Grid**: sm:2 / md:3 / lg:4 columns
- **Better Spacing**: gap-6 untuk breathing room

#### 📱 Footer Comprehensive
- **3 Column Layout**:
  1. About UNU (logo + description)
  2. Quick Links (dengan icons, gold hover)
  3. Social Media (4 platforms + email)
- **Social Buttons**: 
  - White/10 background
  - Hover: gold background + scale
  - Rounded lg design
- **Copyright Section**: 
  - Border top separator
  - Heart icon for "developed with love"

### 🎨 CSS Animations Added
```css
@keyframes backgroundMove: 30s translate pattern
@keyframes backgroundZoom: 20s scale + rotate
@keyframes float: 6s logo levitation
@keyframes gradientShift: 3s gold text animation
```

### 🎯 Design Philosophy
- **Klasik Modern**: Traditional elements (gold, logo) + modern tech (animations)
- **Simple & Clean**: No overload, fokus pada konten penting
- **Professional**: Corporate university branding
- **Dramatic Contrast**: Dark bg + gold accents = premium feel

### 📱 Responsive Implementation
- **Mobile** (< 768px): h-40 logo, text-3xl, 1 col gallery, stacked layout
- **Tablet** (768-1024px): h-40 logo, text-4xl, 2-3 col, horizontal nav
- **Desktop** (> 1024px): h-48 logo, text-4xl, 4 col gallery, full width

### ♿ Accessibility Improvements
- Semantic HTML5 structure
- WCAG compliant color contrast ratios
- Alt texts on all images
- Focus states pada interactive elements
- Touch-friendly button sizes (min 44x44px)

### ⚡ Performance Optimizations
- GPU-accelerated CSS animations (transform, opacity)
- Inline SVG pattern (no HTTP request)
- CSS-only animations (no JavaScript overhead)
- Optimized gradient calculations

### 📁 Files Modified
- `frontend/index.html` - Complete landing page redesign
  - New hero section dengan animations
  - Enhanced features section
  - Improved gallery section
  - Comprehensive footer
- Cache version updated: `app.js?v=3.0`

### 📚 Documentation Created
- `LANDING_PAGE_UPDATE.md` - Detailed implementation guide
- `VISUAL_GUIDE.md` - Visual structure dan color scheme reference

### 🎨 Color Palette Finalized
```
Primary: #1e3a8a (Deep Blue UNU)
Gold: #d4af37 (Official UNU Gold)
Dark: #0f172a (Slate 900)
Gradients: Multiple for various elements
```

---

## 🔄 Previous Update (6 November 2025) - Bug Fixes

### ✅ Bug Fixes
- **Fixed JavaScript Error**: Menghapus duplikasi deklarasi `const CONFIG` yang menyebabkan "Identifier 'CONFIG' has already been declared"
- **Cleaned up app.js**: File JavaScript sekarang lebih clean dan terstruktur tanpa duplikasi code

### 🎨 UI/UX Improvements
- **Logo Kampus**: Mengganti icon generic dengan logo resmi UNU Yogyakarta
  - Logo ditampilkan di navbar landing page
  - Logo ditampilkan di top bar viewer (dengan filter white untuk kontras)
  - Logo dijadikan favicon website
  
### 📁 File Changes
- `frontend/app.js` - Dibuat ulang tanpa duplikasi, struktur lebih rapi
- `frontend/index.html` - Update logo di navbar dan top bar viewer
- `frontend/logo-unu.png` - Logo kampus UNU Yogyakarta yang baru ditambahkan

### 🚀 Konsep Aplikasi
Berdasarkan feedback terbaru, aplikasi difokuskan pada:

1. **Simple Gallery-Based Navigation**
   - Landing page dengan hero section (mirip website UNU)
   - Gallery grid untuk semua lokasi
   - Klik thumbnail untuk buka viewer 360°

2. **Single Scene Viewer**
   - Satu lokasi per view (NO hotspot navigation antar scene)
   - Info sidebar selalu visible
   - Info points (icon) untuk informasi tambahan di gambar

3. **No Complex Navigation**
   - Admin tidak perlu atur pitch/yaw untuk navigation hotspots
   - Fokus ke konten dan informasi, bukan navigasi kompleks
   - Best practice untuk kemudahan maintenance

### ⚠️ Notes
- Tailwind CDN warning untuk production: Normal untuk development, nanti untuk production bisa install via npm
- File `app-old.js` dan `app-old-error.js` adalah backup dari versi sebelumnya

---

## 📝 Next Steps
- ✅ Landing page hero section redesigned (COMPLETED)
- ✅ Simplifikasi UI dengan best practices (COMPLETED)
- 🔄 Backend revisions (pending user requirements)
- 🔄 Testing & refinements based on user feedback
