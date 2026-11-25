# Eutopia4D

An open source pipeline for turning video into textured geometry and registered camera poses, with a browser viewer for exploring the result.

| Component | Role |
| --- | --- |
| Capture builder | Samples frames with FFmpeg, reconstructs geometry with RealityKit, and records provenance and camera poses. |
| Browser viewer | Loads the resulting OBJ and materials, supports free movement, and compares a reconstruction with its source frames when available. |

## Use the viewer

Serve this directory over HTTP and open the project root. Select a capture or open `?scene=demo` for the included synthetic geometry sample. Click the scene, use W/A/S/D to move, drag to turn, and use Q/E to descend or rise.

## Build a capture

The viewer requires WebGL. The capture builder requires Python 3.11+, FFmpeg, Xcode Command Line Tools, and macOS 14+ on hardware supporting RealityKit Object Capture.

```sh
python3 tools/capture/build.py /path/to/recording.mov my-scene \
  --fps 2 --detail medium --source "Creator, location, date, and footage rights"
```

Serve the directory and open `?scene=my-scene`. Use input footage you have permission to process and check redistribution rights before sharing generated captures.

## Release scope and licensing

This snapshot contains the capture pipeline, viewer, and an original synthetic example. Earth, Plaza Mayor, street scenes, and the private development history are outside this release. The sample demonstrates navigation and asset loading. It does not benchmark reconstruction quality.

Original Strata code and documentation are provided under [MIT](LICENSE). The bundled Three.js files retain their [upstream MIT notice](vendor/three/LICENSE).
