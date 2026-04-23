---
name: Organic Vitality
colors:
  surface: '#fff7fd'
  surface-dim: '#e0d7df'
  surface-bright: '#fff7fd'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#faf1f9'
  surface-container: '#f4ebf3'
  surface-container-high: '#eee6ee'
  surface-container-highest: '#e8e0e8'
  on-surface: '#1e1a20'
  on-surface-variant: '#4b4450'
  inverse-surface: '#332f35'
  inverse-on-surface: '#f7eef6'
  outline: '#7d7481'
  outline-variant: '#cec3d1'
  surface-tint: '#764aa0'
  primary: '#390663'
  on-primary: '#ffffff'
  primary-container: '#51247a'
  on-primary-container: '#c192ee'
  inverse-primary: '#ddb7ff'
  secondary: '#6a577a'
  on-secondary: '#ffffff'
  secondary-container: '#edd4fe'
  on-secondary-container: '#6d597d'
  tertiary: '#342300'
  on-tertiary: '#ffffff'
  tertiary-container: '#503700'
  on-tertiary-container: '#c5a061'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#f0dbff'
  primary-fixed-dim: '#ddb7ff'
  on-primary-fixed: '#2c0050'
  on-primary-fixed-variant: '#5d3186'
  secondary-fixed: '#f1daff'
  secondary-fixed-dim: '#d6bee7'
  on-secondary-fixed: '#251433'
  on-secondary-fixed-variant: '#523f61'
  tertiary-fixed: '#ffdea9'
  tertiary-fixed-dim: '#e8c17e'
  on-tertiary-fixed: '#271900'
  on-tertiary-fixed-variant: '#5d420a'
  background: '#fff7fd'
  on-background: '#1e1a20'
  surface-variant: '#e8e0e8'
typography:
  headline-xl:
    fontFamily: Plus Jakarta Sans
    fontSize: 40px
    fontWeight: '800'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '700'
    lineHeight: '1.3'
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '700'
    lineHeight: '1.4'
  body-lg:
    fontFamily: Be Vietnam Pro
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Be Vietnam Pro
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.5'
  label-bold:
    fontFamily: Be Vietnam Pro
    fontSize: 14px
    fontWeight: '700'
    lineHeight: '1.2'
  label-sm:
    fontFamily: Be Vietnam Pro
    fontSize: 12px
    fontWeight: '500'
    lineHeight: '1.2'
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 40px
  xl: 64px
  container-padding: 20px
  gutter: 16px
---

## Brand & Style
The brand personality is rooted in "active stewardship"—it is optimistic, urgent, and deeply community-oriented. This design system avoids the clinical aesthetic often associated with environmentalism, instead opting for a "Lush Modernism" style. It combines high-quality whitespace with sophisticated, muted color splashes to evoke the richness of a bountiful, heirloom harvest.

The interface should feel tactile and "alive." Use high-resolution photography of fresh produce and prepared meals to ground the digital experience in the physical world. The emotional goal is to move the user from the guilt of waste to the joy of discovery and contribution through a more refined, premium lens.

## Colors
This design system utilizes a "Refined Harvest Palette." The primary lavender (#9063bb) provides a modern, approachable take on organic richness. The system is grounded by a deep purple seed (#51247A), ensuring that the generated tonal ranges feel sophisticated, floral, and premium.

The secondary muted mauve acts as a sophisticated anchor for supportive elements, while the tertiary deep bronze (#503700) is reserved for high-impact grounding moments, such as highlighting value-driven "Save Now" opportunities. The background is a tinted off-white rather than pure white, reducing eye strain and feeling more organic. All neutrals are slightly warmed with gray and slate undertones to maintain a friendly, grounded atmosphere.

## Typography
The typography strategy prioritizes approachability and modern flair. **Plus Jakarta Sans** provides a geometric energy for headlines with soft terminal curves that feel welcoming. **Be Vietnam Pro** is used for all functional text; its contemporary proportions ensure high legibility even in dense lists of food items or map labels.

For numerical data (like prices or weight saved), use the headline font in bold weights to make the impact of the user’s actions feel substantial and celebrated.

## Layout & Spacing
The layout employs a flexible 8px-based rhythmic system. On mobile, a 4-column fluid grid is used with generous 20px side margins to allow the content to breathe. 

Components should utilize "grouped density"—information related to a single food item should be tightly packed, while distinct items or map markers should have significant white space between them to prevent the UI from feeling cluttered. The map interface should occupy a full-bleed view or a large-radius container to emphasize exploration.

## Elevation & Depth
This design system uses "Ambient Tonal Layering" to create hierarchy. Rather than harsh black shadows, elevations are indicated by subtle shifts in surface color and very soft, diffused shadows tinted with the seed deep purple (#51247A) at 5-10% opacity.

Floating Action Buttons (FABs) and active "Claim" cards use a secondary layer of depth with a light-source-driven shadow to suggest they are "within reach." Interactive map callouts should appear to float slightly above the terrain using a medium-blur shadow, ensuring they are the primary focal point during navigation.

## Shapes
The shape language is "Organic-Geometric." The standard corner radius is 0.5rem (8px), but container elements like cards and search bars should utilize the `rounded-xl` (24px) or even pill-shaped properties to mimic the softness of natural forms. 

Avoid sharp 90-degree angles entirely, as they feel too corporate and rigid for an app centered on food and community. Buttons should be pill-shaped to maximize the "tap-ability" and friendly aesthetic.

## Components
### Search & Filtering
The search bar is a prominent, pill-shaped element at the top of the interface. Use a soft inner shadow to give it a "recessed" look. Filtering chips should use a light lavender tint when active, with a clear "x" icon to dismiss.

### Maps
The map interface uses a custom-styled base layer (de-saturated tones). Markers are custom-shaped—circular with a small "tail"—and contain icons representing the food category (e.g., a bread icon for a bakery). When a marker is tapped, it expands into a "Peek Card" at the bottom of the screen.

### Buttons & CTAs
The primary Action Button is "The Hero." It uses the primary lavender with white text and a subtle gradient to give it a slightly convex, pressable feel. Critical CTAs like "Reserve Extra Bite" should be full-width on mobile to ensure ease of use.

### Item Cards
Food item cards feature a large image at the top with a "Distance" badge in the corner. The "Original Price" should be shown in a struck-through, muted gray, while the "Extra Bite Price" is displayed in the bold tertiary bronze (#503700) to highlight the value.

### Impact Progress Bars
Unique to this design system, progress bars (showing food saved) use a thick, rounded track with a rich lavender fill and a subtle sparkle animation upon completion.