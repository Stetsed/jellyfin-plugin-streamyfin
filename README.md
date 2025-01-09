## Companion app for [Streamyfin](https://github.com/fredrikburmester/streamyfin)

Allows centralised configuration of Streamyfin.

Config example:

```yaml
home:
  sections:
    Trending:
      style: portrait
      type: row 
      items:
        args: 
          sortBy: AddedDate
          sortOrder: Ascending
          filterByGenre: [""Anime"", ""Comics""]";
```

repo url: https://raw.githubusercontent.com/streamyfin/jellyfin-plugin-streamyfin/main/manifest.json

### Create release

- bump version in makefile
- run `make release`
- commit and push changes made release script