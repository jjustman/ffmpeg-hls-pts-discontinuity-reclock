FFmpeg HLS PTS discontinuity patches for seamless HLS->MPEG-TS or HLS->RTMP re-streaming

contact: jjustman@nbgp.org

Developer configuration:

./configure --enable-static --disable-optimizations --disable-mmx --disable-stripping --enable-debug=3 --enable-pthreads

Testing:

From your favorite discontinious HLS feed, use the following as an example:

ffmpeg -i http://artifacts.ngbp.org/hls/pts-discontinuity.m3u8 -codec copy -f mepgts udp://127.0.0.1:31337; 
ffplay udp://127.0.0.1:31337

or

ffmpeg -i http://artifacts.ngbp.org/hls/pts-discontinuity.m3u8 -vcodec copy -ar 44100 -ac libfaac -f flv rtmp://127.0.0.1:31338/test/stream -rtmp_listen 0;
ffplay rtmp://127.0.0.1:31338/test/stream

Revision History:
2019-01-18 - First public branch



