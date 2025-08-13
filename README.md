Introduction

jQuery Music Player is a web application that plays music using the HTML5 <audio> element.

The interface includes:

Playlist on the left (all tracks)

Right panel showing Current track, Next track, and play progress
It provides Play/Pause/Stop, Next/Prev, Seek, Volume controls, and visual state for the active track.

File Structure
index.html – Main markup and container for the player

css/styles.css – Styles for the playlist, right panel, and controls

js/app.js – Initialization, loading the playlist, binding events

js/player.js – Controls for <audio> (play/pause/stop, next/prev, seek, volume)

js/playlist.js – Rendering and managing the playlist (select, highlight)

assets/audio/ – Audio files (mp3/ogg)

assets/img/ – (Optional) covers/icons

Features
Play / Pause / Stop

Current Track – cover/title/artist in the right panel

Next Track – shown below the current track

Progress bar + current time / duration, with seek on click/drag

Next / Prev and Auto-advance at the end of a track

Volume + Mute

Shuffle and Repeat (off / one / all) (optional)

Active playlist item highlighting

Loading state when switching tracks

How It Works
HTML5 Audio – a single <audio> element controls playback.

jQuery Events – clicking a playlist item → player.play(index).

State Management – currentIndex and nextIndex are updated modularly.

UI Sync – timeupdate, ended, loadedmetadata events update progress, times, and the “Current / Next” panel.

Components (JS)
player.js

load(track) – sets audio source and metadata

play(index?), pause(), stop()

next(), prev(), seek(percentage), setVolume(value)

emits custom events for UI updates (player:changed, player:progress)

playlist.js

render(tracks) – displays the list on the left

highlight(index) – marks the active track

onSelect(cb) – callback on track selection

app.js

defines tracks[] (title, artist, src, cover)

binds control buttons (Play/Pause/Stop/Next/Prev/Shuffle/Repeat)

updates the right panel: Current & Next


view demo: https://meek-frangollo-f29b85.netlify.app/
