## Companion app for [Streamyfin](https://github.com/fredrikburmester/streamyfin)

Allows centralised configuration of Streamyfin.

Config example:

```yaml
# You can remove any settings you do not need configured.

# Format Example
# settingName:
#   locked: true | false # if true, locks the setting from modification in app. Default false.
#   value: value # Value you want the setting to be. Editor will give you type suggestion for a specific setting.

# Example below shows all supported settings at this time.
settings:
  # Media Controls, this is the amount of seconds it will skip forwards and backwards with the media controls.
  forwardSkipTime: 
    value: 30
  rewindSkipTime: 
    value: 30

  # Audio Controls, specifying true here means that it will keep the audio selected in a stream for future streams.
  rememberAudioSelections: 
    value: false
  
  # Subtitle mode is either Default(0), Always(1), OnlyForced(2), None(3), Smart(4), 
  # Subtitle selection will keep the language subtitle settings for future streams, and subtitle size is the
  # size that is used to render the subtitles, warning that using too high of a value of this with PGS subs can cause blurry
  subtitleMode:
  rememberSubtitleSelections: 
    value: false
  subtitleSize: 
    value: 60
  
  # Other
  # Auto-rotate uses the OS system to control the orientation of the screen, this will usually be the one you want to use.
  autoRotate: 
    value: true

  # Default Video Rotation is incompatible with autoRotate, and will lock it to a certain set of directions.
  # Options: Default(0), All(1), Portrait(2), PortraitUp(3), PortraitDown(4), Landscape(5), LandscapeLeft(6), LandscapeRight(7)
  defaultVideoOrientation:
    value: 0

  # Safe area means that if you click in certain usually accidental areas it will not open the controls.
  safeAreaInControlsEnabled:
    value: true

  # This allows you to display the jellyfin custom menu links from jellyfin web in the streamyfin app, this can be used to add direct Radarr/Sonarr for example.
  showCustomMenuLinks:
    value: false

  # Species what libraries you want to make hidden from the server, specified in an array ["Library1", "Library2"]
  hiddenLibraries:
    value: ["Library1", "Library2"]

  # Enables/Disables the haptic feedback from the interface
  disableHapticFeedback:
    value: false
  
  # Specify the download method, can either be OPTIMIZED or REMUX. OPTIMIZED will make use of the Optimized Server Version so you also need to specify the URL
  downloadMethod:
    value: REMUX
  optimizedVersionsServerUrl:
  # Specifies the maximum number of downloads that should be done at any time.
  remuxConcurrentLimit:
    value: 1
  # If set to true it will automatically download after a optimization request has finished
  autoDownload:
    value: true

  # Jellyseerr URL for Integration
  jellyseerrServerUrl:
  
  # Search engine that is used, either Marlin or Jellyfin. Marlin will also require specifying the URL.
  searchEngine:
    value: Jellyfin
  marlinServerUrl:

  # Popular Lists, set to true to use the popular plugin for more features.
  usePopularPlugin:
  mediaListCollectionIds:

  # Misc.
  libraryOptions:
```

#### Supported Streamyfin App configurations

[Settings.cs](Jellyfin.Plugin.Streamyfin/Configuration/Settings/Settings.cs)

repo url: <https://raw.githubusercontent.com/streamyfin/jellyfin-plugin-streamyfin/main/manifest.json>

### Create release

- bump version in makefile
- run `make release`
- commit and push changes made release script
