![Flatpak](flatpak.png)

A few tests and PoCs while the platform, SDK and extensions are still in fast-paced development.

**Use at your own discretion, I take no responsibility if anything goes wrong.**

[Flatpak](https://flatpak.org), [mpv](https://mpv.io), [ffmpeg](https://www.ffmpeg.org), [youtube-dl](https://github.com/rg3/youtube-dl)


### Usage

```
flatpak run --command=mpv test.flatpak.MediaCenter "It 😤 works 😤 $ です $ áéíóú 🌌 filename 😤 example.mkv"
flatpak run --command=mpv test.flatpak.MediaCenter https://www.youtube.com/watch?v={ID}
```

```
flatpak run --command=youtube-dl test.flatpak.MediaCenter https://www.youtube.com/watch?v={ID}
```

```
flatpak run --command=ffmpeg test.flatpak.MediaCenter -i in.mp3 out.ogg
```


### Notes

Purely educational project.

* Needs testing.
* Each repo should be pinned to a release and builds should be improved (e.g. `cleanup`).
* [ffmpeg](https://github.com/FFmpeg/FFmpeg/blob/master/configure) should be trimmed down to decrease the attack surface.
* There should be a way to manage GUI instances (avoid creating new namespaces).
* If you allow mpv and youtube-dl to access your `.config` folder things *might* get a little confusing. There's XDG user directories, `$MPV_HOME`, `config-dir`, [path interpretation](https://mpv.io/manual/master/#paths) (and MuJS/LuaJIT scripts), `--filesystem`, `--env`. I really dislike `.var`.
* Reading the [VLC](https://github.com/flathub/org.videolan.VLC) package and [this](https://github.com/tingping/flatpak-packages) repo helped a lot.


### .test

[https://tools.ietf.org/html/rfc2606](https://tools.ietf.org/html/rfc2606#section-2)
