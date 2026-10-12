# Trace
Phone-first local tracking test. Live camera or local video, anonymous session IDs, visible live tracking FPS, and optional center zoom scan for small objects. No video upload, recording, face identification, helmet, speed or theft feature.

## Limits
YOLOX Nano COCO categories are predictions, not ground truth. Person age is unknown. Child/adult and exact car make/model are not supported. Anonymous track IDs can switch after occlusion or among similar objects. Center zoom increases detail but slows inference and does not fix blur or missing pixels. Long-gap person re-identification is not implemented.

## Checks (October 12, 2026)
One 50-frame, 10-second development road clip, three manually identified people at 26 checkpoints: old greedy tracker had 2 ID changes, new full-frame tracker had 0; no missing checkpoint in either. Across detected people, lost-track events 34 -> 31; visible detections 268 -> 319. These counts are development evidence on a used clip, not an accuracy score.
Zoom scan adds detections but can fragment tracks. Neither real-phone speed nor CCTV reliability is measured yet. Desktop Chrome at phone layout: roughly 7-8 tracking FPS full frame and 3-4 with zoom; device results will differ.
Functional checks: model loading, camera start/stop, local-video input, reset, camera selection, zoom toggle, storage/privacy cleanup, no horizontal overflow at 320/390/1280px, no JS errors on tested flows. No server uploads.

## Dependencies
YOLOX Nano original public pretrained ONNX, Megvii, Apache-2.0. ONNX Runtime Web 1.20.1, Microsoft, MIT. Copies of licences and credits included. Tracker code is original. No Ultralytics/AGPL code/weights.
