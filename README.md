🎵 OBS Hymnal & Lyric Controller

A lightweight, completely self-contained web application designed specifically to run inside OBS Studio. Manage, schedule, and display hymn and worship song lyrics on your live stream with absolutely zero backend required.

Because all the logic, styling, and data management is contained in a single HTML file, it is incredibly fast and highly secure.

✨ Features

1. Dual-Mode Auto-Detection: The app automatically knows where it is based on window size. Open it in a narrow OBS Dock, and it becomes the Controller. Open it in a wide 16:9 OBS Browser Source, and it becomes the Lyric Output.

2. OBS Native Styling: The controller uses the classic OBS "Yami" dark theme, making it look and feel like a native plugin.

3. Real-Time Sync: Uses browser BroadcastChannel and localStorage to instantly sync lyrics from the controller dock to your stream output.

4. Service Scheduling: Build a setlist of up to 10 songs for quick access during a service.

5. Library Management: Add custom songs via a built-in form, or bulk-import/export your entire database using JSON files or the "Paste JSON" tool.

6. Keyboard Navigation: Fully control your stream without clicking.

🚀 Installation & Hosting

Because this is a static single-file React app, hosting is 100% free and requires no server setup.

Using GitHub Pages (Recommended):

1. Fork or clone this repository.

2. Ensure the main file is named index.html.

3. Go to your repository Settings > Pages.

4. Under "Source", select main (or master) branch and click Save.

5. GitHub will provide you with a live URL (e.g., https://yourusername.github.io/obs-hymnal/).

Alternatively, you can drag and drop the folder containing index.html into Netlify Drop for instant, free hosting.

🎛️ How to Setup in OBS

For the sync to work perfectly, you must use the exact same URL for both the Dock and the Source.

1. Set up the Controller (The Dock)

  1. Open OBS Studio.
  2. In the top menu, go to Docks > Custom Browser Docks...
  3. Under Dock Name, type Lyric Controller.
  4. Under URL, paste your live URL (e.g., https://yourusername.github.io/obs-hymnal/).
  5. Click Apply. A new window will pop up. Dock this window anywhere in your OBS workspace.

2. Set up the Output (The Screen)

  1. In your OBS Sources panel, click the + button and select Browser.
  2. Name it Lyrics Output.
  3. Paste the exact same URL you used for the dock.
  4. Set Width to 1920 and Height to 1080 (or whatever your stream resolution is).
  5. Check the box that says "Refresh browser when scene becomes active".
  6. Click OK.

⌨️ Keyboard Shortcuts

When clicked inside the Controller Dock, you can use the following shortcuts:

- Search Dropdown: Type a song number/name, use Arrow Up / Arrow Down to scroll, and press Enter to load the song.
- Next Slide: Spacebar, Arrow Right, or Page Down
- Previous Slide: Arrow Left or Page Up
- Hide Lyrics from Stream: Escape
- Show Lyrics on Stream: Enter

📁 Managing the Database (JSON)

All songs are saved locally to your browser's storage. You can back up your library at any time by clicking Export JSON.

If you want to paste songs in manually via the Paste JSON button, they must follow this exact format:

{
  "1": {
    "title": "Amazing Grace",
    "verses": [
      "Amazing grace! how sweet the sound,\nThat saved a wretch like me!\nI once was lost, but now am found,\nWas blind, but now I see.",
      "Twas grace that taught my heart to fear,\nAnd grace my fears relieved;\nHow precious did that grace appear\nThe hour I first believed!"
    ],
    "chorus": "This is an optional chorus\nThat will repeat after every verse.",
    "bridge": "This is an optional bridge."
  }
}


🛠️ Built With

- React 18 (via CDN)
- Babel Standalone
- Plain CSS

📄 License

This project is open-source and free to use for any church, ministry, or personal broadcast.
