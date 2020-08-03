# Config.swift

Tiny wrapper/functions for creating a configuration struct that can be read from file.

The structure of this might not be a good idea, currently testing/learning swift.

## Idea

The following config.json:

```json
{
  "name": "sample",
  "people": ["Kristoffer Andreas Dalby"],
  "resolutions": [1200, 1000, 800, 300],
  "jpegCompression": 0.2,
  "inputPath": "sample",
  "outputPath": "out",
  "fileExtentions": ["jpg", "jpeg", "JPG", "JPEG"]
}
```

Can be read into a struct in Swift:

```swift
import Config

public struct GalleryConfiguration: Configuration {
    var name: String
    var people: [String]
    var resolutions: [Int]
    var jpegCompression: Double
    var inputPath: String
    var outputPath: String
    var fileExtentions: [String]
}

let config = Config.readConfig(configFormat: GalleryConfiguration.self, atPath: "config.json")
```
