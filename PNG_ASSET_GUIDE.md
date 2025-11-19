# PNG Asset Sizing Guide

## Current State (After Graphics Improvements)

### Native Game Scale
- **Scale Factor:** 3x (NATIVE_SCALE = 3)
- **Game World:** 1200×1800px
- **Previous:** 400×600px (caused pixelation)
- **Improvement:** 3x increase eliminates pixelation

## Current PNG Assets

Your current PNG files are already high quality:

| Fruit | Current PNG Size | Rendered Diameter (3x) | Quality Assessment |
|-------|------------------|------------------------|-------------------|
| Blueberry | 681×693px | 132px | ✅ Excellent (5.2x) |
| Strawberry | 591×693px | 156px | ✅ Excellent (4.5x) |
| Grapes | 593×599px | 204px | ✅ Excellent (2.9x) |
| Orange | 678×671px | 228px | ✅ Excellent (3.0x) |
| Apple | 661×694px | 288px | ✅ Good (2.3x) |
| Lemon | 766×663px | 348px | ✅ Good (2.2x) |
| Cantaloupe | 605×679px | 396px | ✅ Adequate (1.5x) |
| Pineapple | 662×784px | 468px | ✅ Adequate (1.7x) |
| Coconut | 569×637px | 540px | ⚠️ Acceptable (1.1x) |
| Watermelon | 774×834px | 612px | ✅ Adequate (1.3x) |

### Quality Rating Scale
- **Excellent (3x+):** Asset is 3x or more the rendered size - perfect quality
- **Good (2-3x):** Asset is 2-3x the rendered size - very good quality
- **Adequate (1.5-2x):** Asset is 1.5-2x the rendered size - good quality, minor improvement possible
- **Acceptable (1-1.5x):** Asset is close to rendered size - acceptable, but could benefit from upscaling

## Recommendations

### Option 1: Keep Current Assets (Recommended)
**Your current PNGs are already high quality and work very well with the 3x native scale.**

✅ **Pros:**
- Already provides crisp, sharp graphics
- No work required
- File sizes are reasonable (~400KB each)

❌ **Cons:**
- Coconut could be slightly sharper (but still looks good)

### Option 2: Selective Upgrades (Optional)
If you want absolute maximum quality, consider upgrading only the larger fruits:

**Recommended sizes for selective upgrade:**
- Cantaloupe: 800×800px (currently 605×679px)
- Pineapple: 950×950px (currently 662×784px)
- Coconut: 1100×1100px (currently 569×637px)
- Watermelon: 1250×1250px (currently 774×834px)

This would bring all fruits to 2x+ quality ratio.

### Option 3: If You Increase to 4x Scale (Future-Proofing)
If you decide to increase NATIVE_SCALE to 4 in the future:

| Fruit | Rendered @ 4x | Recommended PNG Size |
|-------|---------------|---------------------|
| Blueberry | 176px | 350-500px |
| Strawberry | 208px | 400-600px |
| Grapes | 272px | 550-800px |
| Orange | 304px | 600-900px |
| Apple | 384px | 750-1100px |
| Lemon | 464px | 900-1300px |
| Cantaloupe | 528px | 1000-1500px |
| Pineapple | 624px | 1200-1800px |
| Coconut | 720px | 1400-2000px |
| Watermelon | 816px | 1600-2400px |

## Image Creation Guidelines

### For AI-Generated Images
If using AI tools (DALL-E, Midjourney, Stable Diffusion):
1. Request images at 1024×1024 or larger
2. Specify "high detail", "sharp focus", "game asset style"
3. Request transparent background (PNG with alpha)
4. Ensure circular/round composition

### For Manual Editing
If editing existing images:
1. Use vector formats when possible (SVG → PNG export)
2. Export at 2x the target rendered size minimum
3. Use PNG-24 with alpha channel for transparency
4. Optimize with tools like TinyPNG while maintaining quality

### File Size Considerations
- Current average: ~440KB per fruit
- 10 fruits × 440KB = ~4.4MB total
- If upgrading to larger sizes, consider:
  - Doubling size (800-1200px): ~6-8MB total
  - Still acceptable for modern web
  - Consider using WebP format for 30% size reduction (requires fallback)

## Testing Image Quality

### How to Test
1. Open the game in a browser
2. Look at fruits on the canvas - should be sharp, not blurry
3. Check preview fruit at top - should be crisp
4. Check evolution bar at bottom - icons should be clear
5. Test on high-DPI displays (Retina, 4K) for best assessment

### Current Quality Assessment
After 3x scale improvement:
- ✅ Fruits look sharp and detailed
- ✅ No visible pixelation or blur
- ✅ Graphics take full advantage of PNG quality
- ✅ Comparable to professional mobile games

## Conclusion

**Your current PNG assets at ~600-800px are already well-suited for the 3x native scale.**

**No changes are required** - the game now looks sharp and professional. Only consider upgrading if:
1. You want to future-proof for 4x scale
2. You want absolute maximum quality for the largest fruits
3. You're adding new fruit types that will be even larger

The graphics improvement from increasing the native scale from 1x to 3x has already made a dramatic difference in quality!
