# Maui-basic-VLC-Player-Tutorial 1

# 🎬 MauiVLCPlayer 1

A cross-platform .NET MAUI app using **LibVLCSharp** to play MP4 and HLS video streams. Built with **Visual Studio 2022** and **.NET 8**, this project demonstrates how to integrate VLC’s powerful media engine into a modern mobile/desktop UI.

Please note this is very basic and only a way for you to get started i spenk weeks trying to get this far Maui is still very experimental in my opinon. I thought it would be nice to share what I learned here.
I plann on continuing with controls and things and cossider this to be part 1. Stay tuned for Part 2.

---

https://github.com/user-attachments/assets/bb8e35d7-10a0-4566-bb94-99f899287758



## 🚀 Getting Started

### ✅ Prerequisites
- Visual Studio 2022 (latest version)
- .NET 8 SDK
- Android emulator or physical device (for testing)

---

### 📦 NuGet Packages

Install the following packages via NuGet:

```bash
LibVLCSharp
LibVLCSharp.MAUI
VideoLAN.LibVLC.Android
VideoLAN.LibVLC.Windows
VideoLAN.LibVLC.iOS
These packages provide cross-platform bindings and native support for VLC playback.

🧱 UI Layout
The app uses a Grid layout with:

Row 0: Control bar with volume slider, mute toggle, fullscreen toggle, and titlebar toggle

Row 1: VideoView that fills remaining space

xml
<Grid.RowDefinitions>
  <RowDefinition Height="Auto" />
  <RowDefinition Height="*" />
</Grid.RowDefinitions>

🧠 Code Highlights 
MauiProgram.cs
csharp
builder.ConfigureMauiHandlers(handlers =>
{
    handlers.AddHandler(typeof(VideoView), typeof(VideoViewHandler));
});
Core.Initialize();
MainPage.xaml.cs
csharp
_libVLC = new LibVLC();
_mediaPlayer = new MediaPlayer(_libVLC);
videoView.MediaPlayer = _mediaPlayer;

_mediaPlayer.Play(new Media(_libVLC,
    "https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8",
    FromType.FromLocation));
Includes volume control, mute toggle, and fullscreen logic (Android-specific).

📺 Demo Stream
The app plays a public HLS stream:

Code
https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8
You can swap this with any .mp4 or .m3u8 URL.

🧩 Next Steps
Add stream switching

Favorites manager

Remote input handling

Auto-hide controls

📷 Screenshots
<img width="1202" height="931" alt="video" src="https://github.com/user-attachments/assets/1aefe6a9-45fb-41c2-b272-41df2bd36c6d" />
Screenshot of playback and control bar in action.

🧑‍💻 Author
Built by Dwain — strategic builder, infrastructure optimizer, and IPTV-native UX architect.

📄 License
MIT License (or your preferred license)

Code Download from code button.

## Support

[![Support this project on Ko-fi](https://img.shields.io/badge/Ko--fi-Support-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/dwainhsnickles)
[![Donate on PayPal](https://img.shields.io/badge/PayPal-Donate-003087?logo=paypal&logoColor=white)](https://paypal.me/YTDPlatinum)

If this project saved you some time, you can leave a tip at
[ko-fi.com/dwainhsnickles](https://ko-fi.com/dwainhsnickles) (cards, no account needed) or
[paypal.me/YTDPlatinum](https://paypal.me/YTDPlatinum). Bug reports and pull requests are welcome too.
