# AGENTS.md

This file provides guidance to agents when working with code in this repository.

## Project Overview
This is a Pomodoro Timer web application - a productivity tool implementing the Pomodoro Technique for time management.

## Project Structure

### Main Files
- [`pomodoro.html`](pomodoro.html:1) - Complete single-page Pomodoro Timer application
  - Self-contained HTML file with embedded CSS and JavaScript
  - No external dependencies or build system required
  - Can be opened directly in any modern web browser

### Other Files
- [`dad.py`](dad.py:1) - Empty Python file (not part of main application)
- `.continue/` - Continue.dev configuration directory

## Application Features

The Pomodoro Timer ([`pomodoro.html`](pomodoro.html:1)) includes:

1. **Timer Modes**
   - Pomodoro: 25 minutes work session
   - Short Break: 5 minutes
   - Long Break: 15 minutes (after 4 pomodoros)

2. **Core Functionality**
   - Start/Pause/Reset controls
   - Visual progress ring indicator
   - Auto-switching between work and break modes
   - Session statistics tracking (completed pomodoros, total minutes)

3. **User Experience**
   - Responsive gradient background design
   - Browser notifications support
   - Audio notification on completion
   - Document title updates with remaining time

## Technical Architecture

### JavaScript Class Structure
- [`PomodoroTimer`](pomodoro.html:219) - Main class managing timer logic
  - Timer state management
  - Mode switching (work/break)
  - Progress tracking and statistics
  - UI updates and notifications

### Key Methods
- [`start()`](pomodoro.html:294) - Begins countdown
- [`pause()`](pomodoro.html:310) - Pauses timer
- [`reset()`](pomodoro.html:317) - Resets to current mode duration
- [`complete()`](pomodoro.html:325) - Handles timer completion
- [`switchMode()`](pomodoro.html:281) - Changes between pomodoro/break modes
- [`updateProgressRing()`](pomodoro.html:261) - Updates SVG progress indicator

### Styling
- Modern gradient background (`linear-gradient(135deg, #667eea 0%, #764ba2 100%)`)
- Card-based centered layout
- Responsive button states with hover effects
- SVG-based circular progress indicator

## Development Guidelines

### Code Style
- ES6+ JavaScript with class-based architecture
- Semantic HTML5 structure
- CSS with modern features (flexbox, animations, gradients)
- Inline styles and scripts for portability

### Making Changes
When modifying the application:
1. **Timer Logic**: Modify the [`PomodoroTimer`](pomodoro.html:219) class methods
2. **Styling**: Update the `<style>` section (lines 7-172)
3. **Layout**: Modify HTML structure (lines 174-216)
4. **Durations**: Adjust [`modes`](pomodoro.html:221) object values (in seconds)

### Testing
- Open [`pomodoro.html`](pomodoro.html:1) directly in a browser
- No build process or server required
- Test all three modes (Pomodoro, Short Break, Long Break)
- Verify notifications work (requires permission grant)
- Check progress ring animation
- Validate statistics tracking

### Browser Compatibility
- Requires modern browser with:
  - ES6 JavaScript support
  - Web Audio API (for sound notifications)
  - Notification API (optional, for browser notifications)
  - SVG support (for progress ring)

## Future Enhancement Ideas
- Customizable timer durations
- Sound selection options
- Task list integration
- Session history/analytics
- Dark mode toggle
- Keyboard shortcuts
- Settings persistence (localStorage)