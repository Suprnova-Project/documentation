# Suprnova CLI

The Suprnova CLI, `supr`, is the official multi-platform command line application for Suprnova. It provides functionality for all Suprnova tasks, but without the ease of use of our [Suprnova GUI](gui.md) application. We strongly recommend using the GUI application instead of `supr`.

## Usage

```bash
Usage: supr  [options] <cmd>

Command Line for Suprnova

Options:
  -v, --version                    output the version number
  -k, --key <key_string>           set the CFS key (default: null)
  -i, --id <id_string>             set the CFS identifier (default: "suprnova/pool")
  -t, --temp <temp_path>           set a non-standard temp path (default: "/tmp")
  -h, --help                       output usage information

Commands:
  add [options] <path>             Adds the given file or directory's contents to a CFS.
  cat <cfs_path>                   Pipes a CFS file to STDOUT
  concat [options] [segments_dir]  Concatenates the segments in a CFS segments dir
  create [profile_name]            Creates a new CFS
  demux <source_file>              Demuxes the declared file and writes the tracks to CFS
  events                           Print the CFS event log
  join <discovery_key>             Join a Suprnova pool
  launch                           Launch a Suprnova pool
  metadata <media_file>            Outputs video metadata to cfs:/home/sources/metadata/
  mux [concat_file]                Muxes the declared concat file into an MP4 container
  segment <media_file>             Segment a file and write the outputs to CFS
```

## Getting Started

### Dependencies

Have ya got a recent version of `ffmpeg` in your PATH? Good, that's all you need!

### Examples

#### Create a new CFS

```bash

$ supr -i test/test create

{"level":30,"time":1535559937623,"msg":"true","pid":22126,"hostname":"littlbox","id":"test/test","key":"ac9b4101cb4829fbe8f58038706d5b08e10c2c5b59c9d104a64e0d0d4bfe5f58","profile":"work","v":1}
```

#### Add `file.mp4` to a CFS

```bash

$ supr -i test/test add file.mp4 -p "sources"

{"level":30,"time":1535560087846,"msg":"file.mp4","pid":22675,"hostname":"littlbox","id":"test/test","key":"ac9b4101cb4829fbe8f58038706d5b08e10c2c5b59c9d104a64e0d0d4bfe5f58","add":"file.mp4","v":1}
```

#### Add a file to CFS via torrent URL
```bash
$ node cli.js -i test/torrent add -t "http://distribution.bbb3d.renderfarming.net/video/mp4/bbb_sunflower_1080p_60fps_normal.mp4.torrent"
```

#### Pipe a file from CFS to stdout

```bash
$ supr -i suprnova/pool cat /home/file.mp4 | mpv -
```

#### Launch a supr pool
```bash
$ supr -i test/test create

{"level":30,"time":1545171832395,"pid":17221,"hostname":"littlbox","id":"test/test","key":"8b3a37f27d366a0ff9d20c1ccc55088b7fa2000a59ff315601c3972d7921adfb","command":"create","success":true,"v":1}

$ supr -i test/test metadata video.mp4

{"level":30,"time":1545171851739,"msg":"/home/metadata/source.json","pid":17637,"hostname":"littlbox","id":"test/test","key":"8b3a37f27d366a0ff9d20c1ccc55088b7fa2000a59ff315601c3972d7921adfb","command":"metadata","file":"video.mp4","v":1}

$ supr -i test/test demux video.mp4

{"level":30,"time":1545171856327,"pid":17749,"hostname":"littlbox","name":"progress","progress":"89","timemark":"00:52:45.28","v":1}
{"level":30,"time":1545171856465,"pid":17749,"hostname":"littlbox","name":"progress","progress":"100","timemark":"00:59:05.79","v":1}
{"level":30,"time":1545171856467,"pid":17749,"hostname":"littlbox","id":"test/test","key":"8b3a37f27d366a0ff9d20c1ccc55088b7fa2000a59ff315601c3972d7921adfb","command":"demux","tracks":["/tmp/tracks-WgYPOZ/track_1_audio.mp4"],"v":1}

$ supr -i test/test segment video.mp4

{"level":30,"time":1545171871273,"pid":17911,"hostname":"littlbox","id":"test/test","key":"8b3a37f27d366a0ff9d20c1ccc55088b7fa2000a59ff315601c3972d7921adfb","command":"segment","opts":{"id":"test/test","key":null,"temp":"/tmp"},"segments":[<LOTS AND LOTS OF SEGMENTS HERE>], "v": 1}

$ supr -i test/test launch

{"level":30,"time":1538671472716,"pid":3252,"hostname":"flybox","name":"pool","tracks":["/tmp/tracks-fpuSoQ/track_1_audio.mp4"],"segmentsAvailable":[<ALL_DEM_SEGMENT_FILES>],"ready":true,"v":1}
{"level":30,"time":1538671472720,"pid":3252,"hostname":"flybox","name":"launch","discoveryKey":"319826a3f4a8c6a9246157e5ddb34211d6c538d0c5a9e8cdc74afe672ea0a1e9","v":1}
{"level":30,"time":1538671472724,"pid":3252,"hostname":"flybox","id":"test/test","key":"567caffcd1d40fdcc1d34c5614e0af830a65cbe25d4fc6d71204a8e26ee3dd2d","command":"launch","v":1}

```

### Tests

Execute `npm test` to run test scripts.
