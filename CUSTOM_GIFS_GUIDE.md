# 🎨 Custom GIF/Meme Guide for WorkWell

## How to Add Your Custom GIFs and Memes

### Step 1: Create an Images Folder
Create a folder called `images` in the same directory as `index.html`:
```
CV desk workout app/
├── index.html
└── images/
    ├── you-got-this.gif
    ├── celebration.gif
    ├── time-to-move.gif
    └── etc...
```

### Step 2: Add Your GIF URLs
Open `index.html` and find the `customMedia` object around line 865. Uncomment and add your GIF paths:

```javascript
const customMedia = {
    motivational: [
        'images/you-got-this.gif',
        'images/keep-going.gif',
        'images/amazing.gif',
    ],
    celebration: [
        'images/celebration.gif',
        'images/high-five.gif',
        'images/winner.gif',
    ],
    reminder: [
        'images/time-to-move.gif',
        'images/stretch-break.gif',
        'images/dont-forget.gif',
    ],
    slacking: [
        'images/disappointed.gif',
        'images/get-moving.gif',
        'images/seriously.gif',
    ]
};
```

### Step 3: Use the Functions

#### Option 1: Full Popup with GIF
Shows a centered popup with your GIF and message:
```javascript
showMotivationalPopup('celebration', 'Amazing work! 🎉');
```

#### Option 2: Small Notification with Image
Shows a corner notification with optional image:
```javascript
showNotificationWithImage('Great job!', 'images/thumbs-up.gif');
```

### Where to Add Them

**1. After Completing Exercise** (line ~1959):
```javascript
// Replace this:
showNotification('Exercise completed! Great job! 💪');

// With this:
showMotivationalPopup('celebration', 'Exercise completed! Great job! 💪');
```

**2. For Reminders** (in `showNotification` function):
```javascript
showMotivationalPopup('reminder', 'Time to stretch and move around!');
```

**3. For Missed Days** (add custom check):
```javascript
// If user hasn't exercised in 2 days
showMotivationalPopup('slacking', 'We miss you! Time to get moving! 💪');
```

**4. For Milestones**:
```javascript
// 5 day streak
showMotivationalPopup('motivational', 'You\'re on fire! 5 days strong! 🔥');

// 10 exercises completed today
showMotivationalPopup('celebration', '10 exercises today! You\'re amazing!');
```

### GIF Categories

- **motivational**: Encouraging, "you got this", positive vibes
- **celebration**: High fives, dancing, success celebrations
- **reminder**: Gentle nudges, time to move, don't forget
- **slacking**: Playful disappointed faces, get moving prompts

### Tips

1. **GIF Size**: Keep GIFs under 2MB for fast loading
2. **Dimensions**: 300-500px width works best
3. **Format**: Both .gif and .webp are supported
4. **Fallback**: If no GIFs added, shows text notification automatically
5. **Random**: App picks random GIF from each category

### Example Sources for GIFs

- GIPHY (download GIFs)
- Tenor (download GIFs)
- Make your own with:
  - Photoshop
  - GIPHY's GIF maker
  - Online GIF creators

### Testing

After adding GIFs:
1. Refresh the page
2. Complete an exercise
3. Check if your celebration GIF appears!

Enjoy customizing your WorkWell experience! 🎉
