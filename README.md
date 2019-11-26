Evo Video Analysis
====

## Tools
- Bento4 (`mp4dump`)
- `qtfaststart` (installed using pip)
- `AtomicParsley`
- `mediainfo`

## Process
In order to see detailed information in `mediainfo-gui`:
- View -> Tree
- Debug -> (Complete, Details)
- Demux -> Elementary streams only

## How to structure blog post
- An introduction of how to read and understand the MP4 file specification and layout using `mediainfo-gui` and some hex editor.
- Explain the Hackaday post by comparing why some applications display different information when showing the sizes of each atom.
- With the previous point, I should mention my hypotesis about the exploitation of this flaw.
- Based on the knowledge acquired in the points above, analyze Evo's video and check the hypotesis.
- Write some recomendations and observations

## Observations about `poc.mp4`
By checking the `poc.mp4` file using `mediainfo-gui` to have a better visbility on a tree-like structure, the `moov` atom contains a `meta` atom of 117 or 0x00000075 bytes. After the `meta` atom definition comes a `hdlr` atom that has a size of 33 or 0x00000021 bytes.
