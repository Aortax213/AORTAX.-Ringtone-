# AORTAX Ringtone App - Design Guidelines

## Design Approach

**Reference-Based Approach**: Drawing inspiration from premium audio platforms like Spotify, Apple Music, and SoundCloud, adapted for a ringtone browsing and download experience. The design emphasizes visual audio representation, seamless discovery, and premium feel.

**Core Principles**:
- Audio-first visual language with waveform representations
- Immersive browsing experience with rich previews
- Premium, modern aesthetic with gradient treatments
- Seamless discovery and instant gratification

---

## Typography System

**Primary Font**: Inter (Google Fonts) - Clean, modern, excellent Arabic support
**Secondary Font**: Cairo (Google Fonts) - For Arabic text, warm and friendly

**Hierarchy**:
- Hero/Display: 48px (mobile), 72px (desktop), bold weight
- Page Titles: 32px (mobile), 48px (desktop), semibold
- Section Headers: 24px (mobile), 32px (desktop), semibold
- Card Titles: 18px, medium weight
- Body Text: 16px, regular weight
- Metadata/Labels: 14px, medium weight
- Captions: 12px, regular weight

**RTL Support**: Full right-to-left layout support for Arabic content

---

## Layout System

**Spacing Primitives**: Tailwind units of 2, 4, 6, 8, 12, and 16
- Component padding: p-4 to p-6
- Section spacing: py-12 (mobile), py-16 (desktop)
- Card gaps: gap-4 to gap-6
- Icon spacing: space-2 to space-4

**Grid System**:
- Mobile: Single column (grid-cols-1)
- Tablet: 2 columns (md:grid-cols-2)
- Desktop: 3-4 columns (lg:grid-cols-3 xl:grid-cols-4)
- Container max-width: max-w-7xl

---

## Page Structure & Components

### Homepage

**Hero Section** (80vh):
- Immersive full-width hero with animated waveform background visualization
- Centered content with app logo, tagline, and prominent search bar
- Floating action buttons with glassmorphism effect (blurred backgrounds)
- Download count badge and trending indicator

**Featured Ringtones Carousel**:
- Large horizontal scrollable cards showcasing top 10 ringtones
- Card design: 280px × 320px with album-art style imagery
- Integrated mini-player controls on hover
- Category badge, title, artist/theme, download count, rating stars

**Category Grid**:
- 6-8 category cards in responsive grid
- Each card: 240px × 180px with representative imagery
- Icon + category name + ringtone count
- Subtle gradient overlays for depth

**Trending Section**:
- Compact list view with numbered rankings
- Inline waveform visualizations
- Quick play buttons and download icons

**New Releases**:
- Grid layout similar to featured but smaller cards (200px × 240px)
- "New" badge with animated pulse effect
- Metadata: upload date, category, downloads

### Browse/Library Page

**Filter Sidebar** (Desktop) / Top Filters (Mobile):
- Category checkboxes with icon representations
- Sort dropdown (Popular, Newest, Most Downloaded, Highest Rated)
- Duration range slider
- Quick filter chips for common selections

**Ringtone Grid**:
- Masonry-style grid for visual interest
- Card hover states reveal play button and action menu
- Card content: Waveform thumbnail, title, category tag, stats row (downloads, rating)
- Quick actions: Play, Download, Favorite heart icon

**Infinite Scroll**: Load more ringtones as user scrolls

### Ringtone Detail Page

**Hero Section** (60vh):
- Large waveform visualization as background
- Centered player interface with oversized play/pause button
- Ringtone title and metadata overlaid with glassmorphism panel
- Primary download button with format selector dropdown

**Advanced Player Controls**:
- Scrubber timeline with precise time markers
- Volume control slider
- Loop toggle
- Speed adjustment (0.5x to 2x)
- Waveform visualization that animates with playback

**Information Panel**:
- Two-column layout (desktop)
- Left: Details (Duration, Format, Size, Upload Date, Category, Tags)
- Right: Download options (MP3, M4R), Share buttons, Report link

**Related Ringtones**:
- Horizontal scrolling carousel
- Similar category or theme recommendations
- Compact cards with quick play

### Favorites Page

**Collection View**:
- User's saved ringtones in grid layout
- Bulk action toolbar (Download All, Create Playlist, Clear)
- Sorting and filtering options
- Empty state with encouraging illustration and browse suggestions

---

## Component Library

### Audio Player Component
- Circular play/pause button (56px diameter)
- Progress bar with gradient fill showing playback position
- Time display (current/total)
- Waveform visualization behind controls
- Volume and additional controls in expanded state

### Ringtone Card
- Aspect ratio 4:5 for vertical cards
- Rounded corners (border-radius: 12px)
- Subtle shadow for depth
- Hover elevation increase
- Image/waveform visual
- Title (truncate at 2 lines)
- Category badge (pill shape)
- Stats row: Download icon + count, Star icon + rating
- Action overlay on hover: Play, Download, Heart icons

### Category Badge
- Pill-shaped with icon + text
- Small (24px height), medium (32px), large (40px) variants
- Subtle background with border

### Search Bar
- Prominent width (max-w-2xl centered)
- Rounded (border-radius: 24px)
- Search icon prefix
- Clear button suffix when typing
- Auto-suggest dropdown with recent searches

### Download Button
- Primary action button with icon
- Dropdown for format selection (MP3, M4R)
- Progress indicator during download
- Success checkmark animation

### Statistics Display
- Icon + number combination
- Compact horizontal layout
- Abbreviated numbers for large counts (e.g., "2.5K", "1.2M")

---

## Icons

**Library**: Heroicons (via CDN)
- Use solid variants for filled states (favorites, downloads)
- Use outline variants for default states
- Consistent 24px size for UI elements
- 20px for inline text icons

**Key Icons**:
- Play/Pause: MusicalNote, PlayCircle, PauseCircle
- Download: ArrowDownTray
- Favorite: Heart (outline/solid)
- Categories: appropriate thematic icons
- Share: Share
- Search: MagnifyingGlass

---

## Images

### Hero Image
**Large hero image required**: Yes
- Full-width abstract waveform visualization or audio-themed gradient art
- Should convey energy, music, and modernity
- Overlay gradient for text readability
- Animated subtle movement (floating particles or wave motion)

### Category Images
- Representative imagery for each category:
  - Music: Musical instruments, notes, DJ equipment
  - Nature: Landscapes, wildlife, natural scenes
  - Classic: Vintage phones, retro aesthetics
  - Modern: Abstract tech, digital art
  - Islamic: Islamic geometric patterns, calligraphy

### Ringtone Thumbnails
- Generated waveform visualizations as primary visuals
- Abstract gradient backgrounds representing audio mood
- Category-specific themed backgrounds
- Size: 400px × 500px minimum for quality

---

## Accessibility

- ARIA labels for all player controls
- Keyboard navigation for audio player (Space: play/pause, Arrow keys: seek)
- Focus indicators on all interactive elements
- Sufficient contrast ratios for text
- Screen reader announcements for playback states
- Alternative text for all images
- Form labels for search and filters

---

## Animations

**Sparingly Applied**:
- Waveform pulse animation during audio playback
- Card hover elevation (transform: translateY(-4px), 200ms ease)
- Button press feedback (scale: 0.95)
- Download success checkmark animation (scale + fade)
- Page transitions: Subtle fade (300ms)
- Loading skeleton screens for content

**No animations on**:
- Background elements
- Decorative graphics
- Excessive scroll-triggered effects

---

## Responsive Breakpoints

- Mobile: < 768px (single column, simplified player)
- Tablet: 768px - 1024px (two columns, full features)
- Desktop: > 1024px (multi-column, expanded controls)

**Mobile Optimizations**:
- Bottom-fixed mini player when scrolling
- Simplified filter interface (bottom sheet)
- Larger touch targets (48px minimum)
- Swipe gestures for favorites

---

This comprehensive design creates a premium, professional ringtone app with audio-first visual language, seamless discovery, and delightful user experience across all devices.