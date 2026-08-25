# Changelog

All notable changes to **AstroSuite Pro**.

This file is generated from the changelog built into the application itself, 
so it always matches what you see under **Help > What's New** in the app.

Versions are listed newest first. Entries prefixed *Beta* pre-date the 1.0.0 
release and use their own numbering.

---

## v1.0.4  *(current)*

- The filename and Rename moved to the end of the Image Editor toolbar. Packed first, the label's width changed with the name and every button after it slid along - so the buttons were never in the same place twice
- The scratch folder is now AstroSuite_Temp and the Siril working folder AstroSuite_Pro_Siril. Clear Temp Files also sweeps the old AstroShed_Temp folder, which nothing else would ever have cleared - only through that explicit, confirmed action, never automatically, since temp can hold a result you have not saved yet
- Renamed to AstroSuite Pro. Settings, profiles and the processing history saved under the old name are moved across the first time it runs, so nothing is lost - and the icon and watermark still resolve if they are only present under their previous filenames
- Help windows open centred on the app rather than parked beside the Process Tools sidebar. That placement exists so a tool dialog does not cover the image being worked on, which is right for a tool and wrong for Help - these have nothing to do with the image
- The About window was 1140px tall and holding four unrelated things. What's New and How Editing Works are now their own Help entries, leaving About with what the word actually means - version, what it is built on, licensing - at a sensible size
- What's New shows the WHOLE history in its own window. It used to be a six-line box inside About, which is no way to read 206 entries across 17 versions, and it marks the version you are running
- The About button has gone from the left panel - the Help menu is where anyone would look, and that panel now collapses, so it was the wrong home for something that should always be reachable
- The Information Panel and Console can be hidden together - the panel icon on the toolbar, Edit > Hide / Show Info + Console, or F8 - giving their height to the image. They share one row, so both go at once. The state is remembered between sessions
- Hover bubbles stay beside the button they belong to. A wide bubble on a tools-sidebar button had to hang far out to the left, over the image and nowhere near what it described - it now right-aligns to the button and wraps narrower
- Toolbar icons show their NAME in the hover bubble - Crop, Image Solver, STF Stretch - rather than the first line of a description. An icon needs naming, not explaining; the explanation stays in the Information Panel
- Check All, Uncheck All, Remove Selected and Clear All had no tooltips at all - being labelled, it was never obvious. They have them now
- Tooltips now also appear as a small bubble under the pointer after a short pause, the way most desktop applications do it - so a button can be learned without looking across to the Information Panel. The bubble shows the first sentence only; the full text stays in the panel, since several run to a paragraph and a paragraph in a bubble is unreadable. Settings > Hover Tooltips turns them off
- Added a before/after compare button to the Image Editor toolbar - click to see the image as it was before any editing, click again to return, with the button outlined while the original is showing. Nothing is changed either way, unlike Undo which has to be reversed afterwards
- View FITS Header added to the icon toolbar as well as the tools sidebar - it is a diagnostic rather than a processing step, and gets reached for often
- Subframe Selector, Blink Tool and Load Stacking Profile added to the Tools menu. They existed only on the left panel, so collapsing it left them unreachable
- Added a menu bar and icon toolbar across the top - File, Edit, Tools, Settings and Help, each dropdown showing its keyboard shortcut in a right-hand column, plus a row of icon buttons for the things done most often. Both sidebars are unchanged. The Tools menu is generated from the same list that builds the tools sidebar, so the two cannot drift apart, and every shortcut the menus advertise is actually bound
- Toolbar icons are now drawn with Pillow at run time instead of using text arrows. The unicode glyphs were hairline strokes meant for equations, so they read as faint scratches at button size and only got worse when enlarged. These are proper shapes, drawn at four times the size and scaled down so the edges stay smooth, with no icon files to ship
- The Image Editor toolbar is now a single row of icons instead of two rows of text buttons. Open, Undo, Redo and Save came off it entirely - they are on the global toolbar now. The Debayer and STF switches and the Linked/Unlinked choice stay as switches and radio buttons, because each carries a state you need to see at a glance
- The Files Viewer / Image Editor switch moved onto the end of the icon toolbar, with an icon each - a framed picture and framed lines of text - and the tab strip is hidden, removing a whole horizontal band of the window that held nothing but two words
- The Image Editor and Files Viewer toolbars moved up into the empty band level with the Add Frames and Process Tools headings, one shown at a time depending on the view. That removes a row from inside both tabs and fills a gap that was doing nothing
- The left panel can now be collapsed - the Hide / Show button on the toolbar, Edit > Hide / Show Left Panel, or F9 - handing its full width to the image. The state is remembered between sessions. Everything on the panel is reachable from the menus, so nothing is lost while it is hidden
- The left panel is shown and hidden from the tabs on the window's left edge, replacing the toolbar button. F9 and Edit > Hide / Show Left Panel still work
- The left edge now carries two tabs, STACKING and HISTORY, which choose what the left column shows. Clicking the tab already showing collapses the column, so hiding it still works the same way
- Added a History view: every tool applied to the image in the Editor, in order, with a click on any step taking you back to how the image looked at that point. The intermediate files are still on disk, so it is a real undo rather than a list - and the steps you go back past move to redo, so nothing is lost
- The History view names the image being worked on, and keeps a permanent record: every tool applied is written to a log beside the settings file, grouped by image and by day. Earlier sessions on the same image appear beneath the current ones, so months later you can see what you did to it and when
- Flip and rotate moved from the Image Editor toolbar up to the main icon toolbar, since they apply to the loaded image whichever tab is in front
- The four display controls - STF stretch, Linked, Unlinked and Debayer - moved from above the Editor onto the icon toolbar as toggles. STF shows as lettering, Linked and Unlinked as joined and broken chain links, Debayer as a half-colour half-mono square, and whichever are active carry a green outline. Linked and Unlinked stay a pair, so exactly one is ever lit
- Auto-Open Result in Editor moved from a switch on the frame list row to a toggle on the icon toolbar, alongside the other display toggles, and is also in the Settings menu with a tick showing its state
- Crop Tool added to the icon toolbar - it is reached for constantly, so it no longer has to be found in the tools sidebar
- Image Solver added to the icon toolbar, next to Advanced Settings and Open Output Folder
- Added zoom in and zoom out buttons to the Image Editor toolbar. Fit and 1:1 jump to fixed levels, so without a mouse wheel there was no way to zoom at all. They step by the same amount as one notch of the wheel
- Start Stacking added to the frame list row, where the rest of the frame actions are - choose your frames, then start - with a wide gap separating it from Clear All so the two cannot be confused
- File menu now offers all four frame types - Lights, Darks, Flats and Bias - plus Smart Import Files and Smart Import Folder, rather than only Lights
- File menu now has Save Image alongside Save Image As. Save Image writes straight back over the file being edited, after confirming - unlike Save As it replaces what is on disk and Undo cannot bring that back
- The frame list buttons - Check All, Uncheck All, Remove Selected, Clear All and Refresh Metrics - are now smaller outlined buttons with drawn icons in the app's accent blue, instead of large solid blue buttons carrying emoji
- Subframe Selector and Blink Tool now use drawn icons like the rest, instead of emoji that rendered noticeably smaller, and the gap between icon and text is even across every sidebar button
- The Open Image icon now shows a picture inside the folder - as a plain folder it was indistinguishable from Open Output Folder sitting a few icons along
- The sidebar buttons that have a toolbar equivalent - Advanced Settings, Open Output Folder, Analyze Frames and Start Stacking - now use the same drawn icons, so the same action looks the same wherever it appears
- The Settings menu has a single Advanced Settings entry that opens the window on click and offers the individual tabs on hover, so you can go straight to Calibration or Alignment rather than opening the window and then finding the tab
- Icon toolbar grouped so the view-related controls sit together at the end - the display toggles and then the Files Viewer / Image Editor switch, after the file, edit and transform actions
- Menu popups are lifted slightly and given a faint blue cast with a brighter border, so an open menu no longer blends into the sidebar behind it
- Redrew the display toggles: the chain links now run diagonally so they read as a chain, the broken one has red bursts at the snap, and Debayer shows the actual Bayer pattern - red, green, green, blue - rather than a generic colour swatch
- Menu bar buttons are now sized to their own text instead of all being the same width - with one fixed width, File sat in a lot of empty space while Settings nearly filled its button, so the gaps between the words looked uneven even though the buttons were evenly spaced
- Added the missing tooltips on the Fit and 1:1 zoom buttons, evened up the spacing between the toolbar icons, and took Start Stacking off the icon toolbar - the sidebar has a full-width button for it, and a one-click start among small icons is too easy to hit by accident
- Collapsing the left panel is a single layout pass now. It used to remove the container and then change the column width as two separate steps, and Tk lays out after each - so the intermediate state was painted, which is the block that flashed on the right and made the buttons ripple leftwards in stages
- Fixed the Tools submenu staying on screen after its parent menu closed - and, because it had no titlebar and sat above everything, not even disappearing when the window was minimised
- Fixed menu clicks falling through to whatever sat underneath - choosing a menu item was also pressing the toolbar button beneath it. The menu acted on the mouse press and destroyed itself while the button was still down, so the release landed on the control below, and CustomTkinter buttons fire on release
- The Image Solver and SPCC dialogs open instantly again - checking whether the image had coordinates was going as far as the online name resolver, so the window waited on a network round-trip before it could appear. The dialogs now read the header only, and the lookup happens when you actually solve
- FIXED: saving a FITS whose header contains lowercase keywords failed. PixInsight's noise evaluation writes cards like medNR-1, and the FITS standard requires uppercase, so astropy refused to write the file back out - which broke Crop and every other tool that saves a FITS, but only on files that had been through PixInsight
- Restored the xisf version shim that had been lost from the source. Without it a built exe dies at startup with PackageNotFoundError, because xisf reads its own package metadata as it imports and PyInstaller bundles the module without it
- Plate solving now reads OBJCTRA/OBJCTDEC as well as RA/DEC and CRVAL - those sexagesimal fields are what most capture software actually writes, and they were being ignored, so an image with perfectly good pointing data could look as though it had none
- The target box takes the object's NAME as well as coordinates - M42, NGC 7000, Rosette Nebula - looked up through the CDS resolver that sits behind SIMBAD. A name is what you actually know about your own image; coordinates are not
- The same target box is now in the SPCC dialog. SPCC plate solves in the background with no chance to intervene, so an image whose header had no pointing data simply failed with nowhere to say where it was pointing
- Added a target coordinates box to the Image Solver, used when the header carries no pointing data at all. Siril cannot solve without a rough starting position, and a stacked master that has been through other software has often lost its RA/Dec - which failed with no way to proceed. The dialog says whether the image already has coordinates, so the box is only needed when it does not

## v1.0.3

- The unsaved results warning on exit no longer counts tool scratch files as results. Running SPCC and undoing it left its working copy behind, so the app warned about unsaved work when the stack had already been autosaved and nothing was at risk
- The star catalogue can also be pointed at a copy you already have, rather than downloading it again - useful if you move the file, already ran Siril's own installer, or keep one copy on a network drive for several machines
- Added an optional offline star catalogue download (Advanced Settings > Maintenance). Plate solving normally queries a server in Strasbourg on every solve - a single server with no mirrors, which fails often enough to stop a run. Download Siril's own Gaia DR3 catalogue once, to a drive of your choosing, and plate solving then works entirely on your own machine. Colour calibration still uses its own online service, which is mirrored eight ways and far more reliable
- FIXED: three of the five stacking methods wrote a command Siril could not run. Median Sigma Clipping, Linear Fit and GESD are rejection TYPES in Siril, not stacking methods, so choosing them would have failed the whole stack. All now work, and Percentile, MAD and no-rejection have been added alongside them
- FIXED: the registration interpolation choices sent the wrong algorithm - Bisquared sent cubic and Bicubic sent lanczos4. They now use Siril's own names, and an existing setting is migrated to whichever algorithm it was really using, so results do not change
- FIXED: the Equalize CFA switch sent Siril's -cfa flag, which is for cosmetic correction, instead of -equalize_cfa which is what equalises the flat's colour channels - so the colour-cast correction the switch promised was never actually applied
- FIXED: the drizzle switches added a -drizzle flag that does not exist on Siril 1.4's stack command. Replaced with the real option, Upscale x2 before stacking. The 3x switch has gone - Siril has no 3x
- Star detection now resets to Siril's defaults at the start of every run. These settings persist inside Siril between sessions, so a value left over from a previous run - or from your own use of the Siril GUI - could previously affect a stack without any indication
- Drizzle on OSC data now works properly as Bayer drizzle - calibration leaves those frames undebayered so Siril can reconstruct colour from the CFA pattern, which its documentation requires and which is where drizzle helps OSC data most. Previously drizzling colour frames handed Siril already-debayered data
- Cosmetic correction now passes -cfa for Bayer data so it examines the correct neighbouring pixels, and cold/hot sigma thresholds are exposed and default to 3/3. Siril's own default detects HOT pixels only, so a switch called Clean Hot & Cold Pixels was previously cleaning half of what its name promised
- The debayer algorithm override now restores your Siril setting on every failure path, including a failed engine launch and an app crash mid-stack - previously those routes could leave your own Siril preference changed with nothing to put it back
- Fixed a thread-safety bug in the Blink Tool: changing the stretch mode built its display images on a background thread, which Tk does not allow. The image processing still happens in the background, but the display objects are now created on the main thread as they should be
- Stacking options that only apply to certain methods are no longer sent with the ones that reject them - normalisation and weighting on Sum, maximize and upscale on Median
- Drizzle now also applies with Mosaic and Intersection framing, not just standard
- Fixed two scrollbars appearing on the Light and Calibration tabs, where the contents could never size themselves properly
- Every option Siril's stack command accepts is now available: all five methods including Minimum and Maximum, all eight rejection types, and all four weighting modes - Background Noise and Frames Stacked were previously unreachable
- Added the rest of Siril's stacking options: equalize colour backgrounds, fast normalisation, force 32-bit output, rejection maps, edge feathering and overlap normalisation - each one only offered to the stacking methods that actually accept it
- Added frame filtering - let Siril leave the worst frames out of the stack by FWHM, weighted FWHM, roundness, background level, star count or quality, as a percentage, a k-sigma multiple or an absolute threshold
- Registration now offers everything Siril's register command accepts: all six interpolation methods, clamping control, the transformation model (homography, affine, similarity, shift), minimum star pairs, maximum stars, and star-list output
- Star detection now exposes search radius, minimum roundness, PSF fit iterations, Gaussian or Moffat model with minimum beta, and relaxed star checks - only the noise threshold was adjustable before
- Drizzle restored, on the registration step where Siril actually implements it, with pixel fraction and kernel choice
- Added a registration output scale (0.1 to 3), sitting with the drizzle options because it is what sets the drizzle factor - 2 for 2x, 3 for 3x. Siril's drizzle flag carries no magnification of its own. It also works without drizzle as a plain rescale, including downscaling for quick test stacks
- Added Centre of Gravity framing, Siril's fourth framing method - keeps more field than Intersection while still giving a clean rectangle
- Added the remaining calibration options: Fuji X-Trans autofocus correction and the choice to calibrate excluded frames
- Every stacking run now ends with a timing summary - each step with its duration, frame count and share of the total, so a run that feels slow can be compared against a previous one instead of guessed at. Also shown when a run fails, so you can see which step it reached
- Added Histogram Transformation - the PixInsight-style stretch, with black, midtone and white handles under a live RGB histogram, the transfer curve drawn against the identity diagonal, and an Auto button that suggests a starting point from the image itself
- The frame list's column headers now explain themselves - hover any of them for a description of what FWHM, Roundness, RMSE, BG Noise and the rest actually measure, and which direction is better
- Removed Upscale x2 before stacking. The Output scale control on the Alignment tab does the same job at registration and does it better - any factor from 0.1 to 3 rather than a fixed 2x, and it is the one drizzle uses. Having both meant they could be enabled together for an unintended 4x
- Reorganised the sidebar's Core Parameters around what actually changes between targets: the Sigma Low and Sigma High rejection sliders moved up from Advanced Settings to sit with the stacking algorithm they belong to, and Framing joined them. Image Weighting stays. Debayer Algorithm moved back to Advanced Settings > RAW/FITS, alongside the note explaining it, since it is a set-once preference rather than a per-target choice
- Moved Pre-Stacking Correction into the Calibration tab, alongside the Master Dark it uses, and removed the now-empty Cosmetic tab
- Renamed the Image Viewer tab to Image Editor, and the Mini Viewer's swap button to Swap with Editor - it is the window the tools actually work on, and the name now says so
- Added a Licensing section to About / Credits - AstroSuite Pro is GPL v3 with its source in every release, and Siril is bundled unmodified with its own licence and AUTHORS file alongside it
- Tool previews can now be zoomed and panned - mouse wheel to zoom, drag to pan, and a Fit button (or a double-click) to see the whole image again. Added to Colour Masks, Dust Lane Enhancer, Dark Structure Enhance, Multiscale Local Contrast and RangeSelection Mask
- Split Channels: the channel boxes no longer say Ha/OIII in full RGB mode - those labels now appear only in duo-band mode, where they are actually true
- Split Channels: synthetic Luminance can now be built from equal weights (default, best signal-to-noise), Rec.709, or CIE L* - it was fixed at Rec.709
- Update notices are now a small box under About / Credits in the sidebar, instead of a dialog opening over the app a few seconds after launch - click it to see what has changed and install. Checking for updates manually still answers straight away with the full dialog
- Added a General / Updates tab to Advanced Settings, holding the app's own behaviour - window, exit and update options
- Added Remember window size and position - turn it off and the app always opens maximized, as before
- Added a warning on exit when a session has results you never saved, with a Don't warn me again option
- Added Reset All Settings, which puts everything back to defaults without touching your profiles or images
- Moved the update controls out of the About dialog into Advanced Settings > General / Updates - the check button and the startup switch now sit together
- Advanced Settings tabs now scroll, so the window no longer has to be as tall as its longest tab
- Temp files are now kept in one folder per session, and everything older than your last session is cleared automatically at startup - the previous session is always kept, whatever its size, so unsaved results are still there to go back to
- Clear Temp Files now clears every session at once, for when you want the space back immediately
- You can now choose how many previous sessions to keep (Advanced Settings > Maintenance) - 0 to 3, with 1 the default
- You can now move the two folders that grow large onto another drive (Advanced Settings > Maintenance): the temp scratch folder, and the stacking working folder that holds calibrated and registered frames. Previously both were fixed to the system drive, which is what filled it up
- Tool windows are now kept on screen - a tall dialog is moved up, and shortened only if it still would not fit, so nothing opens with its buttons below the bottom of the display
- The Process Tools sidebar now reopens the same groups you had open when you last closed the app - switch it off in General / Updates if you prefer everything closed at startup
- Added an interface size adjustment (Advanced Settings > General / Updates) - scales buttons, text and dialogs together, relative to your Windows display scaling

## v1.0.2

- Added an opt-in auto-updater, ready for public releases - set UPDATE_REPO and it switches itself on, leave it empty and it does nothing at all
- Added Correct Magenta Stars - removes the magenta fringing chromatic aberration leaves around stars (Colour Tools)
- Improved the console - Siril progress spam is filtered out, cutting a typical run by about 90 percent
- Fixed Copy Log producing an empty clipboard, and added a Clear Log button beside it
- Added RGB Stars to Narrowband - puts real broadband star colour onto a narrowband image (Star Tools)
- Added Sensor Un-Mix to Split Channels - inverts your sensor's Ha/OIII crosstalk instead of a fixed channel split (linear data only)
- Added the Foraxx palette to Combine LRGB - blends per pixel from the data rather than assigning channels (stretched data only)
- Added Warmth, Tint and Hue Rotation to the Camera RAW Editor, all luminance-preserving
- Added tabs to the Camera RAW Editor so 17 sliders no longer make one very tall window
- Renamed Ratio Palette Synthesis to Dual-Band to SHO - the old name implied a choice of palettes it does not offer
- Improved the Camera RAW preview - Clarity, Texture and Sharpen now show the structure scale Apply will actually produce
- Improved SPCC feedback - a short summary of the fit quality and star counts now prints at the end of a run
- Fixed stacking failing outright when a single master dark, flat or bias was used instead of raw calibration frames
- Fixed a crash when a picker-based tool was opened with an empty viewer and then closed
- Fixed Combine LRGB, NB to RGB Stars, Screen Stars and RGB Stars to NB not explaining that an empty viewer is fine for them
- Fixed the Blink Tool having no tooltip, and widened the file list's Filter column

## v1.0.1

- Added Split Channels - splits an image into separate mono channels, with a duo-band Ha/OIII mode
- Added Pixel Math - applies an arithmetic expression to every pixel, and can combine several open images into a new one
- Added Multiscale Local Contrast - boosts contrast only at the structure sizes you select
- Added Ratio Palette Synthesis - turns a duo-band image into a gold-and-teal SHO-style palette
- Added 90 degree rotation, clockwise and anticlockwise, beside Flip H/V
- Added a Show Background toggle to Background Extraction and to GraXpert
- Added a Match Luminance to Colour slider to Combine LRGB
- Added an OIII from control to Ratio Palette Synthesis - green only, or the average of green and blue
- Added an in-dialog mask preview to Color Masks
- Added a faint app-logo watermark to the empty main viewer and file list
- Added multi-file opening everywhere - the Open button, drag and drop, the file list, and auto-open after stacking
- Added Enter as a shortcut to open the selected rows in the file list
- Added a Save As button to the Mini Viewer toolbar
- Rebuilt the Process Tools sidebar as collapsible drawers with plain buttons
- Rebuilt Combine LRGB's channel selection, and applied the same simpler picker to NB to RGB Stars and Screen Stars
- Moved the information panel and console into a single bottom bar, matched in height
- Moved settings and saved profiles to a fixed per-user folder in AppData
- Improved Multiscale Local Contrast, Dark Structure Enhance and Dust Lane Enhancer with a side-by-side preview layout
- Improved SCNR's Preserve Lightness to match Bill Blanshan's Modified SCNR v4
- Improved Combine LRGB and NB to RGB Stars so sources are read-only and nothing overwrites a master
- Improved the Save Result dialog - the Overwrite button now names the file it would replace
- Improved the stars-only image from StarXTerminator - it now opens straight into a Mini Viewer with STF off
- Sped up Multiscale Local Contrast, Star Reduction's preview, and 90 degree rotation
- Fixed SCNR producing magenta artefacts on stars and bright areas
- Fixed the SCNR Amount slider being permanently stuck at 0.70
- Fixed Combine LRGB needing every source picked twice, and going mono when a Luminance channel was added
- Fixed Mini Viewers appearing to duplicate when the app was minimized and restored, and the crash when closing one
- Fixed Mini Viewers not appearing in the source dropdowns
- Fixed the white flash when dialogs and the main window open
- Fixed Ratio Palette Synthesis losing saturation on Apply, showing too little teal, and appearing to apply twice
- Fixed a blue halo in the sky around every object
- Fixed a startup crash and the watermark never staying visible
- Fixed rotation and flip corrupting the working image
- Removed the collapsible left stacking sidebar - it worked, but flashed on collapse and is parked for now

## v1.0.0

- Rebuilt the app as a single window instead of a separate popup for the viewer
- Added Dark Structure Enhance and Dust Lane Enhancer for bringing out dust and dark structure
- Added Blemish Blaster, Star Stretch and NBtoRGB Stars, ported from Franklin Marek's Seti Astro scripts
- Added VeraLux HyperMetric Stretch, ported from Riccardo Paterniti's original
- Added RangeSelection Mask and an app-wide masking system, so any tool can be applied through a mask
- Added Astro Color Mixer - hue-targeted colour and luminance adjustment
- Added Camera RAW Editor, expanded from the original Brightness/Contrast/Sharpen tool
- Added LinearFit, Background Neutralization and Color Saturation
- Added Bin/Downscale, Flip Horizontal/Vertical, and a Preview Region tool
- Added Image Solver as a standalone plate-solve tool alongside SPCC
- Added the Subframe Selector dashboard with Stars, FWHM and Roundness charts, usable before stacking
- Added an Analyze Frames button and a Roundness column to the file list
- Added a Readout bar below the viewer showing pixel values under the cursor
- Added Mini Viewer windows, with Swap, minimize-to-icon and drag-and-drop loading
- Added the ability to rename images within the app, so channels can be labelled Ha, OIII or SII
- Added XISF support throughout - open, edit and save
- Added drag-and-drop image loading to the main viewer and every Mini Viewer
- Added SII + OIII as a filter pair for dual-band extraction, alongside Ha + OIII
- Added mono image support to every tool where it makes sense
- Added apply-this-crop-to-other-open-images to the Crop tool
- Added auto-align to Combine RGB, and channel pickers that can take any open image
- Split the Process Tools sidebar into five labelled groups
- Renamed Combine RGB to Combine LRGB / Narrowband, and Compare to Mini Viewer
- Changed every toggle switch, radio button and checkbox from blue to green when enabled
- Improved tooltips app-wide - larger hover targets, no flicker, and none missing
- Improved live previews across 15 dialogs so they match what Apply actually produces
- Improved the metrics table with a real per-frame noise measurement
- Fixed a widespread crash affecting 48 places across nearly every tool
- Fixed Debayer silently corrupting mono images if left on from a previous load
- Fixed white flashes when dialogs, the main window and the Subframe Selector open
- Fixed windows taking several seconds to close
- Fixed the Save button greying out after every save
- Fixed dark haloing around stars during noise-aware stretching
- Fixed the built .exe's own icon not showing in the taskbar and title bar
- Fixed the Blink Tool re-reading every file from disk on each toggle, and needing Debayer set manually
- Fixed the metrics table showing nothing after a stack, and the first frame never getting a Roundness reading
- Fixed two stacking bugs found in real runs - darks not shared across filters, and a mismatched sequence
- Fixed the STF Stretch toggle not actually skipping the stretch when turned off
- Removed Noise-Aware Stretch after measurement showed it was not earning its place
- Ran a full code audit with two static analyzers and fixed everything they found

## Beta 12

- Added a Mini Viewer (🔍 Mini Viewer... button) - a second, independent viewer window for looking at another image side by side, e.g. inspecting separate R/G/B masters while combining them. View-only (zoom, pan, STF Stretch) - no editing tools, doesn't touch the main viewer, and you can open as many as you like
- Color Masks now offers 12 colours instead of 6 (added Orange, Chartreuse, Spring Green, Azure, Violet, Rose) - the original 6 are Bill Blanshan's own PixelMath, the 6 in-between colours use the same verified formula centred on a different hue
- Added Color Masks - Bill Blanshan's hue-based colour masking (Red/Yellow/Green/Cyan/Blue/Magenta), ported from his actual PixelMath source, with adjustable Strength and Blur plus an Invert Mask toggle (on by default). Applies a saturation adjustment blended by the mask, so it only affects the chosen colour - protects everything else, matching how these are normally used in PixInsight

## Beta 11

- GHS, Curves, Star Reduction, and Combine RGB windows now live-resize to fit whatever's actually visible - switching to a mode with fewer controls shrinks the window, switching to one with more grows it, instead of a fixed size with wasted space

## Beta 10

- Added Combine RGB - combines separate mono master images (e.g. from a mono camera, or individual narrowband filters) into one colour image, with an optional Luminance layer for LRGB/LSHO-style results. Custom mode assigns any three images to Red/Green/Blue directly; HOO/SHO/HSO/HOS presets map narrowband filters automatically using this app's existing established channel convention (matching Narrowband Normalization's own mapping)

## Beta 9

- GHS: added the multi-function graphical display from PixInsight's own GHS module - a live histogram + transformation curve, hover to read Transform(x) anywhere on it, click to set a readout value and send it to Symmetry Point or Black Point
- GHS: Stretch Amount is now parametrized as PixInsight's own 'Stretch factor (ln(D+1))', giving much finer control at the low end where most stretches actually happen
- GHS: added Colour Blend (blends between a full Colour-mode transform and a plain per-channel one, per the published spec)
- GHS: added Low/High Clip Proportion (LCP/HCP) for the Linear type - live readout of what % of pixels would clip at the current Black/White Point, and the reverse: set a target clip % and have it calculate the corresponding point

## Beta 8

- Rebuilt Star Reduction from scratch - the previous version's own DIY approach was genuinely broken (confirmed by testing: little visible effect at normal settings, black artifacts in star cores at strong settings). Now a faithful, verified port of Bill Blanshan's actual published Star Reduction PixelMath methods (Transfer/Halo/Star), which recombine an original image with a separately-generated starless image (e.g. from StarXTerminator) rather than trying to detect and shrink stars directly
- Fixed Star Reduction auto-filling the wrong image into 'Original Image' right after running StarXTerminator (it grabbed whatever the viewer was currently showing, which by then is the starless result, not the original) - now remembers the actual original+starless pairing from the moment StarX runs, and only offers it back when it's confirmed still relevant

## Beta 7

- Added Screen Stars - recombines a starless image with a separately-processed stars-only image, using Bill Blanshan & Mike Cranfield's published ScreenStars technique (verified round-trip against the unscreen math StarXTerminator/StarNet use)

## Beta 6

- Added Star Reduction - shrinks/dims stars without removing them, built from scratch (masked morphological erosion), with live preview

## Beta 5

- Added a native GHS tool built from scratch from the published GHS specification (David Payne & Mike Cranfield) - Generalized Hyperbolic, Midtone Transfer, Arcsinh, Power Law, and Linear all in one tool, with Colour/Lightness/Saturation modes, live preview, and no Siril round-trip
- This replaces the Siril-scripted GHS, Modified Arcsinh, Histogram Transformation, and Linear Stretch tools, which are now all covered by the one native tool
- Added a native Curves tool (Full RGB, Individual RGB, Luminance Only, Saturation) with an interactive draggable curve editor and live preview

## Beta 4

- Added Narrowband Normalization (Bill Blanshan & Mike Cranfield's process) and Apply Stretch tools to the image viewer, both with live preview
- STF Stretch now works like PixInsight's own STF - computes its curve once and reuses it, instead of recalculating on every render
- Fixed several image viewer display bugs found along the way (linear data handling, raw sub-exposure bit depth, toolbar/tool-dialog coordination)

## Beta 3

- Added Undo/Redo and a manual Save button to the image viewer
- Image viewer can now be opened independently of the frame list, with drag & drop support for adding frames
- Added a global crash handler, temp file cleanup, and a startup check for missing tool paths
- Added an STF Stretch toggle to view the raw linear data vs the auto-stretched preview

## Beta 2

- Added GraXpert integration (Background Extraction and Denoising)
- Added a Crop Tool with direct Python/astropy cropping
- Moved SPCC from an automatic step to a manual, on-demand one

## Beta 1

- Added RC-Astro Xterminator Tools (BlurXTerminator, StarXTerminator, NoiseXTerminator)
- Added manual Background Extraction

---

AstroSuite Pro is free software released under the [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.html). 
The full source code is included in every release download.
