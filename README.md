# hlsVideoPlayer

video js and hls video player example

first we should convert the vide using this command:

ffmpeg -i big.mp4 -b:v 1M -g 60 -hls_time 2 -hls_list_size 0 -hls_segment_size 500000 output.m3u8

- -ffmpeg: This is the command-line tool for handling multimedia processing.

- -i big.mp4: This specifies the input file (big.mp4), which is the source video you want to convert.

- -b:v 1M: This sets the video bitrate to 1 megabit per second. It controls the quality of the video; higher bitrates generally result in higher quality but larger file sizes.

- -g 60: This sets the group of pictures (GOP) size. The GOP is a sequence of frames that are interrelated. In this case, a new GOP will start every 60 frames.

- -hls_time 2: This sets the duration of each segment in the HLS playlist to 2 seconds. HLS divides the video into segments, and this option specifies how long each segment should be.

- -hls_list_size 0: This sets the maximum number of entries in the master playlist (output.m3u8). A value of 0 means there is no limit. The master playlist is the main playlist that references all the other playlists and segments.

- -hls_segment_size 500000: This sets the size of each individual segment in bytes. In this case, each segment will be approximately 500 kilobytes.

- output.m3u8: This is the output file that will be generated. It's the master playlist file for HLS streaming.
