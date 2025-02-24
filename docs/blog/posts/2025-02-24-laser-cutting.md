---
date: 2025-02-24
categories:
    - DIY
---

# Laser Cutting Guide

## TinkerCAD Controls

-   **View Movement**: Shift + Right Click
-   **View Rotation**: Right Click
-   **Alignment**: Center Center
-   **Movement Precision**: Adjust Snapgrid (bottom right)
-   **Export Format**: .svg

## Inkscape Setup

1. Create New File

    - Format: A3 Landscape

2. File Import
    - Import SVG (avoid direct opening)
    - Select imported objects: Ctrl + A
    - Set Fill/Stroke: RGB(0,0,0), 1px

## Engraving Process

1. Isolate engraving object
2. Extensions > 305 Engineering > Generate engraving files
3. File naming: E\_[filename]
4. Restore other objects (Ctrl + Z)
5. Remove engraving elements

## Cutting Process

1. Extensions > Generate Laser G codes
2. File naming: C\_[filename]

## Machine Operation

1. Insert SD card
2. Set home position
3. Configure power/speed multiplier
4. Secure material with masking tape
5. Execute engraving before cutting

## Best Practices

-   Add lines/patterns on left/right sides to prevent burnt edges from laser slowdown
-   Follow engraving-then-cutting sequence
