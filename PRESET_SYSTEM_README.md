# Hearing Aid App - Preset Management System

## Overview

This hearing aid app now includes a comprehensive preset management system that allows users to:
- Save custom parametric equalizer configurations
- Load predefined and custom presets
- Add and remove custom EQ filter bands dynamically
- Manage presets (rename, delete)

## Features

### 1. Preset Management

#### Save Presets
- **Button**: "Save" button in the Parametric EQ section
- **Function**: Saves the current EQ settings, master volume, noise gate, and compression settings as a named preset
- **Storage**: Presets are stored persistently using SharedPreferences in JSON format

#### Load Presets
- **Button**: "Load" button in the Parametric EQ section
- **Function**: Opens a dialog showing all available presets
- **Presets Included**:
  - **Flat**: Neutral response with no EQ adjustments
  - **Speech Clarity**: Optimized for understanding speech with boosted mid-range frequencies
  - **Bass Boost**: Enhanced low-frequency response
  - **High Freq Loss**: Designed for users with high-frequency hearing loss (common in aging)
  - **Music**: Balanced EQ for music listening

#### Preset Options
- **Long-press** on any preset in the load dialog to access:
  - Load preset
  - Delete preset
  - Rename preset

#### Delete Multiple Presets
- Click the "Delete" button in the load dialog
- Select multiple presets to delete at once

### 2. Custom Filter Management

#### Add Custom Filters
- **Button**: "Add Filter" button in the Parametric EQ section
- **Parameters**:
  - **Frequency**: 20 Hz to 20,000 Hz (enter custom value)
  - **Gain**: -20 dB to +20 dB (adjustable with slider)
  - **Q Factor**: 0.1 to 10.0 (adjustable with slider)
- **Function**: Dynamically adds a new EQ band to the audio processing chain

### 3. Current Preset Display
- Shows the currently active preset name
- Displays "Custom" when manual adjustments are made to any parameter
- Located below the preset management buttons

## Technical Implementation

### Files Created

1. **EQPreset.kt**
   - Data class for storing preset information
   - Includes JSON serialization/deserialization
   - Contains default preset definitions

2. **PresetManager.kt**
   - Handles preset storage and retrieval
   - Uses SharedPreferences for persistent storage
   - Provides preset management operations (save, load, delete, rename)

3. **Dialog Layouts**
   - `dialog_save_preset.xml`: Save preset name input
   - `dialog_preset_list.xml`: Display and manage presets
   - `dialog_add_filter.xml`: Add custom EQ filter

### Updated Files

1. **AudioEngine.kt**
   - Changed from fixed 4-band EQ to dynamic EQ bands
   - Added methods: `addEQBand()`, `removeEQBand()`, `applyPreset()`, `getCurrentState()`
   - Supports unlimited EQ bands (performance permitting)

2. **MainActivity.kt**
   - Added preset management UI controls
   - Integrated PresetManager
   - Added dialog handlers for preset operations
   - Automatic "Custom" marking when parameters are manually adjusted

3. **activity_main.xml**
   - Added three buttons: Load, Save, Add Filter
   - Added current preset display TextView

4. **build.gradle.kts**
   - Added Material Components library for TextInputLayout

## Usage Guide

### Saving a Custom Preset

1. Adjust the EQ bands, master volume, noise gate, and compression to your preference
2. Click the "Save" button
3. Enter a name for your preset
4. Click "Save" in the dialog

### Loading a Preset

1. Click the "Load" button
2. Tap on any preset name to load it
3. The UI will update to reflect the preset's settings
4. The current preset name will be displayed

### Adding a Custom Filter

1. Click the "Add Filter" button
2. Enter the frequency (e.g., 500 for 500 Hz)
3. Adjust the gain slider (-20 dB to +20 dB)
4. Adjust the Q factor slider (0.1 to 10.0)
5. Click "Add" to create the filter

### Managing Presets

1. Click the "Load" button to open the preset list
2. **Long-press** on any preset to:
   - Load it immediately
   - Delete it
   - Rename it
3. Or click the "Delete" button to select multiple presets to delete

### Customizing Loaded Presets

- After loading a preset, any manual adjustment will mark it as "Custom"
- You can save these modifications as a new preset using the "Save" button

## Preset Data Structure

Each preset stores:
- **Name**: User-defined or default name
- **Filters**: Array of filter bands with:
  - Frequency (Hz)
  - Gain (dB)
  - Q factor
  - Enabled state
- **Master Volume**: Amplification gain
- **Noise Gate Threshold**: Background noise suppression level
- **Compression Ratio**: Dynamic range compression
- **Timestamp**: Creation/modification time

## Storage

- Presets are stored in SharedPreferences under the key `eq_presets`
- Format: JSON array of preset objects
- Current active preset name is stored separately
- Storage persists across app restarts

## Future Enhancements

Potential improvements:
- Export/import presets to files for sharing
- Cloud backup of presets
- Visual EQ curve display
- Ability to remove individual filter bands from UI
- Preset categories and tags
- A/B comparison between presets
- Undo/redo functionality

## Notes

- The existing 4 fixed EQ bands in the UI continue to work as before
- Custom filters added via "Add Filter" are managed internally but not displayed in the static UI
- The audio engine supports an unlimited number of filters (within performance limits)
- All parameters are automatically saved when creating a preset
- Presets are stored locally on the device
