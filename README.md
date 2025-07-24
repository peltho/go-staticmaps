# go-staticmaps
A go (golang) library and command line tool to render static map images using OpenStreetMap (amongst others) tiles.

## Why this fork
This is a fork of [go-staticmaps](https://github.com/flopp/go-staticmaps) intended to remove TLS security check when downloading tiles.

It's an answer to a corner case when you are using a custom tile provider.

For instance:
```golang
var customProvider *sm.TileProvider
customProvider = &sm.TileProvider{
    Name:        "custom",
    Attribution: "",
    TileSize:    512,
    URLPattern:  "your-custom-raster-tile-provider-url/%[2]d/%[3]d/%[4]d.png",
    Shards:      []string{"a", "b", "c"},
}
```
