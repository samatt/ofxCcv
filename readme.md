# ofxCcv

![](https://farm8.staticflickr.com/7415/16250786748_f0e3984e19_o.png)

This is an addon for openFrameworks that wraps the computer vision library [libccv](libccv.org). The goal is to experiment with a few features that distinguish libccv from OpenCv, like the deep convolutional neural net implementation. ofxCcv may be merged with ofxCv to provide as much power as possible in a single addon without requiring developers to keep track of which library they are using.

This addon is not yet very easy to use. You will need to do a number of unusual things:

1. Clone openFrameworks for 64-bit OS X from [kylemcdonald/feature-64bit](https://github.com/kylemcdonald/openFrameworks/tree/feature-64bit) which is based on work from [prisonerjohn/feature-64bit](https://github.com/prisonerjohn/openFrameworks/tree/feature-64bit) with some minor modifications that I hacked in and don't totally understand.
2. Download and install [CUDA developer toolkit](https://developer.nvidia.com/cuda-toolkit) (currently at version 6.5).
3. Clone this repository into `openFrameworks/addons/`
4. Download [libccv](http://libccv.org/) and build `libccv.a` in the way I describe [here](https://github.com/liuliu/ccv/issues/131#issue-56143724).
5. Move and rename `libccv.a` to `openFrameworks/addons/ofxCcv/libs/ccv/lib/ccv.a`.
6. Copy `image-net-2012.sqlite3` (or `image-net-2012-vgg-d.sqlite3`) and `image-net-2012.words` into `openFrameworks/addons/ofxCcv/example/bin/data/`. Both these files should come with libccv. One comes in the repo, the other is downloaded when running `make`.
7. Build and run the example project.

These instructions are from memory and may be incomplete. I can't speak to the process for doing this on Windows, but it's possibly very similar (and probably easier) on Linux.