# CHANGELOG

## 2025-09-29

### prototype-index.html Enhancements

#### Header Improvements
- Implemented scroll-triggered header visibility
  - Header initially hidden to reduce redundancy with hero section
  - Smoothly reveals after scrolling 100px
  - Includes performance optimizations with scroll debouncing

#### Hero Section Updates
- Increased logo size from 300px to 400px (500px on desktop)
- Changed layout to center-aligned for better visual hierarchy
- Set hero section to 85vh height to ensure Connect section visibility
- Optimized responsive sizing with max-height constraints

#### Connect Section - Refined UX
- Removed progressive disclosure pattern for better UX consistency
- Contact email now always visible (no hidden state)
- Connect heading click smoothly scrolls to center the section
- Added smooth scroll behavior for all anchor links
- Consistent navigation behavior across all Connect links

#### Design Decisions
- Chose center alignment for authority and symmetry
- Fixed UX inconsistency where Connect heading had different behavior than nav links
- Optimized vertical spacing to keep key content above the fold
- Maintained brutalist aesthetic while improving usability
