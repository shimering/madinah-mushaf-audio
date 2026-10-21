# Audio storage cleanup — 21 October 2026

Full playback now uses chronological ranges into the existing clips. Audio is unchanged; no lossy re-encoding was performed.

| Edition | Duplicate full files removed | Bytes in duplicate full files | Action |
| --- | ---: | ---: | --- |
| 018-الكهف-youtube-v1 | 15 | 536,168,809 | Reuse existing clips |
| 020-طه | 9 | 330,974,323 | Entire Islamweb Ta-Ha edition retired at user request |
| 020-طه-youtube-v1 | 17 | 926,635,582 | Reuse existing clips |
| 049-الحجرات-youtube-v1 | 5 | 79,484,204 | Reuse existing clips |
| 078-النبأ | 1 | 84,978,532 | Reuse existing clips |

The cleanup removes 38 full recordings from active editions and all 149 files of the retired Islamweb Ta-Ha edition (including its nine full recordings). Local source/export MP3s and verification evidence are retained.

- Unique current audio before: **3,917,015,879 bytes** (3.92 GB).
- Unique current audio after: **1,627,711,571 bytes** (1.63 GB).
- Removed unique audio from the current tree: **2,289,304,308 bytes** (2.29 GB; 58.4%).

Counts deduplicate by SHA-256. Existing numbered aliases with identical content share a Git blob, so deleting those aliases would not reclaim additional Git blob storage. Future exports reference one canonical file for shared ayahs.

## History and compatibility

A normal deletion preserves older commits and audio blobs. These figures describe the current published audio tree, **not reclaimed historical Git storage or GitHub's reported repository size**. No history rewrite or force-push was performed. Historical cleanup requires a separate, explicitly authorized operation, a recoverable backup, and a list of only the retired/duplicate paths or blobs. GitHub may retain unreachable objects until its own cleanup occurs.

Older Android builds that embed the removed full-recording URLs need an app update. Existing active ayah and topic URLs are preserved. The updated app uses `schemaVersion: 2` and honors `startMs`/`endMs`. Optional M3U8 files require VLC start/stop support.

Internal joins were verified by matching compressed MP3 packets to the original lessons, then checking complete source coverage and a non-overlapping partition of every reused recording. This technical verification does not replace the previously pending human listening review.
