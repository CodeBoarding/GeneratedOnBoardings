## Media I/O Component Overview

This component handles the input and output of media, including video capture from webcams, reading video files, and writing processed video to disk. It provides frames to the Video Processing component and saves the final output.

```mermaid
dataflow
    subgraph Media I/O
    A[Video Capturer] -- captures --> B(Frames)
    C[Frame Extractor] -- extracts --> B
    B -- sends --> D[Video Processing]
    D -- sends --> E(Processed Frames)
    E -- creates --> F[Video Creator]
    E -- restores audio --> G[Audio Restorer]
    F -- saves --> H(Output Video)
    G -- saves --> H
    I[Temporary File Manager] -- manages --> B
    I -- manages --> E
    J[Capturer] -- gets total frames --> K(Frame Total)
    end


```

## Components

- **Video Capturer**
  - *Description*: Captures video from a webcam, providing frames for processing. It uses `cv2` to access the webcam and reads frames. It can set a callback function to process each frame as it's captured.
  - *Interaction*: Captures frames and sends them to the Video Processing component. Interacts with the Temporary File Manager for storing temporary frames.
  - *Relevant source files*: `modules.video_capture.VideoCapturer`, `modules.video_capture.VideoCapturer.start`, `modules.video_capture.VideoCapturer.read`, `modules.video_capture.VideoCapturer.release`, `modules.video_capture.VideoCapturer.set_frame_callback`

- **Frame Extractor**
  - *Description*: Extracts individual frames from a video file. It uses `ffmpeg` to decode the video and save each frame as an image file in a temporary directory.
  - *Interaction*: Extracts frames from a video file and sends them to the Video Processing component. Interacts with the Temporary File Manager for storing temporary frames.
  - *Relevant source files*: `modules.utilities.extract_frames`

- **Video Creator**
  - *Description*: Creates a video file from a series of image frames. It uses `ffmpeg` to encode the frames into a video file.
  - *Interaction*: Receives processed frames from the Video Processing component and creates a video file. Interacts with the Temporary File Manager for accessing temporary frames.
  - *Relevant source files*: `modules.utilities.create_video`

- **Audio Restorer**
  - *Description*: Restores audio from the original video to the processed video. It uses `ffmpeg` to combine the processed video with the original audio stream.
  - *Interaction*: Combines the processed video with the original audio and saves the final output. 
  - *Relevant source files*: `modules.utilities.restore_audio`

- **Temporary File Manager**
  - *Description*: Manages temporary files and directories for frame storage and processing. It creates temporary directories, moves files, and cleans up temporary files after processing.
  - *Interaction*: Provides temporary storage for frames extracted by the Frame Extractor and used by the Video Creator. 
  - *Relevant source files*: `modules.utilities.create_temp`, `modules.utilities.move_temp`, `modules.utilities.clean_temp`, `modules.utilities.get_temp_directory_path`, `modules.utilities.get_temp_output_path`, `modules.utilities.get_temp_frame_paths`

- **Capturer**
  - *Description*: Provides functionality for getting video frame total.
  - *Interaction*: Gets the total number of frames in a video file.
  - *Relevant source files*: `modules.capturer.get_video_frame_total`
