# AM Bypass ALAC / Dolby Atmos Downloader

Original script by Sorrow. Modified by me to include some fixes and improvements.

## How to use
1. Install a WSA with Magisk build : https://github.com/MustardChef/WSABuilds
2. Install this version of Apple Music: https://www.apkmirror.com/apk/apple/apple-music/apple-music-3-6-0-beta-release/apple-music-3-6-0-beta-4-android-apk-download/. You will also need SAI to install it: https://f-droid.org/pt_BR/packages/com.aefyr.sai.fdroid/.
3. Launch Apple Music and sign in to your account. Subscription required.
4. Port forward 10020 TCP: `adb forward tcp:10020 tcp:10020`.
5. Install and start frida server : https://frida.re/docs/android/
6. Start the frida agent: `frida -U -l agent.js -f com.apple.android.music`.
7. Start downloading some albums: `go run main.go https://music.apple.com/us/album/whenever-you-need-somebody-2022-remaster/1624945511`.
8. Start downloading singles: `go run main_select.go https://music.apple.com/us/album/whenever-you-need-somebody-2022-remaster/1624945511` input numbers separated by spaces.
9. Start downloading some playlists: `go run main.go https://music.apple.com/us/playlist/taylor-swift-essentials/pl.3950454ced8c45a3b0cc693c2a7db97b` or `go run main.go https://music.apple.com/us/playlist/hi-res-lossless-24-bit-192khz/pl.u-MDAWvpjt38370N`.
10. For dolby atmos: `go run main_atmos.go https://music.apple.com/us/album/1989-taylors-version-deluxe/1713845538`.

## Downloading lyrics
1. Open [Apple Music](https://music.apple.com) and log in
2. Open the Developer tools, Click `Application -> Storage -> Cookies -> https://music.apple.com`
3. Find the cookie named `media-user-token` and copy its value
4. Paste the cookie value obtained in step 3 into the config.yaml and save it
5. Start the script as usual
