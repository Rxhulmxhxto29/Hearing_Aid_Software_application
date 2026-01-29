# Quick Start Guide - Preset Management

## Getting Started

### First Time Setup
When you first open the app after this update, you'll see:
- Three new buttons in the Parametric EQ section: **Load**, **Save**, **Add Filter**
- A text showing "Current: Custom" below the buttons
- Five default presets automatically loaded

### Quick Actions

#### 📥 Load a Preset
```
1. Tap "Load" button
2. Select from available presets:
   - Flat (neutral)
   - Speech Clarity (boost speech frequencies)
   - Bass Boost (enhanced low end)
   - High Freq Loss (compensate for hearing loss)
   - Music (balanced for music)
3. Preset applies immediately
```

#### 💾 Save Your Settings
```
1. Adjust EQ, volume, noise gate, compression
2. Tap "Save" button
3. Enter a name (e.g., "My Office Setting")
4. Tap "Save"
5. Your settings are now saved!
```

#### ➕ Add Extra Filters
```
1. Tap "Add Filter" button
2. Enter frequency (e.g., 500 for 500 Hz)
3. Slide Gain to adjust boost/cut
4. Slide Q Factor to adjust bandwidth
5. Tap "Add"
6. Filter is active immediately
```

## Common Use Cases

### 1. Different Environments
Save separate presets for:
- **Home**: Comfortable listening settings
- **Office**: Speech clarity with noise gate
- **Outdoors**: Boosted volume and compression
- **Music**: Enhanced bass and treble

### 2. Medical Audiogram
Create a custom preset based on your hearing test:
```
Example for mild high-frequency loss:
- 250 Hz: 0 dB
- 1000 Hz: +3 dB
- 2000 Hz: +6 dB
- 4000 Hz: +10 dB
- 8000 Hz: +12 dB

Add additional filters at specific frequencies from your audiogram
```

### 3. Activity-Based Settings
- **TV Watching**: Boost speech frequencies (1-4 kHz)
- **Phone Calls**: Heavy mid-range boost with noise gate
- **Concerts**: Reduced volume with compression

## Advanced Features

### Preset Management
- **Long-press** any preset to see options
- **Rename**: Change preset name
- **Delete**: Remove unwanted presets
- **Multi-delete**: Use Delete button for batch removal

### Custom Indicator
- When you manually adjust any slider, the display shows "Custom"
- This tells you the current settings don't match any saved preset
- Save as new preset or reload previous preset

## Tips & Tricks

### 🎯 Fine-Tuning
1. Start with a default preset
2. Make small adjustments
3. Save as "PresetName - Modified"

### 🔄 A/B Comparison
1. Save current settings as "Test A"
2. Make changes
3. Save as "Test B"
4. Switch between them to compare

### 🎚️ Q Factor Guide
- **Low Q (0.1-0.5)**: Wide, gentle curve (affects more frequencies)
- **Medium Q (0.7-1.5)**: Standard, natural sound
- **High Q (2.0+)**: Narrow, surgical (affects specific frequency)

### 📊 Frequency Guide
- **20-60 Hz**: Sub-bass (rumble, thunder)
- **60-250 Hz**: Bass (drums, bass guitar)
- **250-500 Hz**: Low-mid (body, warmth)
- **500-2000 Hz**: Mid (vocals, most instruments)
- **2000-4000 Hz**: High-mid (clarity, presence)
- **4000-8000 Hz**: Treble (detail, consonants)
- **8000-20000 Hz**: Air (brilliance, space)

## Troubleshooting

### Preset Won't Save
- Ensure you entered a preset name
- Check if name already exists (will overwrite)

### Can't Find Saved Preset
- Check the Load dialog
- Presets are sorted alphabetically

### Too Many Filters (Performance Issues)
- Remove unused custom filters
- Stick to 4-8 bands for best performance

### Settings Keep Showing "Custom"
- This is normal when manually adjusting
- Load a preset to sync with saved settings

## Examples

### Example 1: Office Preset
```
Name: "Office - Speech Focus"
Band 1 (250 Hz): -3 dB
Band 2 (1000 Hz): +8 dB
Band 3 (3000 Hz): +10 dB
Band 4 (8000 Hz): +4 dB
Master Volume: 120%
Noise Gate: 3%
Compression: 60%
```

### Example 2: Music Lover Preset
```
Name: "Music - Rich Sound"
Band 1 (60 Hz): +6 dB (Q: 1.2)
Band 2 (250 Hz): +3 dB
Band 3 (1000 Hz): -2 dB
Band 4 (4000 Hz): +5 dB
Band 5 (12000 Hz): +8 dB (custom filter)
Master Volume: 110%
Noise Gate: 0%
Compression: 30%
```

### Example 3: High Frequency Loss
```
Name: "Age-Related Loss Compensation"
Band 1 (250 Hz): 0 dB
Band 2 (1000 Hz): +4 dB
Band 3 (2000 Hz): +8 dB (custom filter)
Band 4 (4000 Hz): +12 dB
Band 5 (8000 Hz): +16 dB
Master Volume: 150%
Noise Gate: 2%
Compression: 70%
```

## Safety Notes

⚠️ **Important**:
- Start with lower volumes and gradually increase
- High gain settings can damage hearing further
- Take breaks during extended use
- Consult an audiologist for proper hearing assessment
- Don't use while driving or operating machinery

## Support

For issues or questions:
1. Check this guide first
2. Review the PRESET_SYSTEM_README.md for technical details
3. Restart the app if presets aren't loading
4. Clear app data to reset to default presets (will lose custom presets)
