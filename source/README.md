# Muhasabah — source code

The complete source of the Muhasabah Android app (`Muhasabah-source.zip`), published under the
GNU Affero General Public License v3.0 (see `LICENSE-AGPL-3.0.txt`), because the app includes the
NudeNet body-part detection model, which is AGPL-3.0.

Third-party parts:
- NudeNet 3 "320n" model — notAI-tech, AGPL-3.0 (`assets/nudenet320.bin`, converted to float16)
- nsfwjs MobileNetV2 model — Infinite Red / GantMan, MIT (`assets/nsfw_mv2.bin`)

Fonts are not included (third-party): put the Arabic and Gujarati fonts named in `src/.../Fonts.java` into `assets/fonts/`.

Build: `tools/build.sh` (no Gradle; needs the Android SDK tools named in the script and your own signing key).
The release signing key is not part of this source.
