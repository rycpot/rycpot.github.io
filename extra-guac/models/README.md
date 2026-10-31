# Photo model

Remove background's model for photos (`u2netp-<n>.bin`), downloaded by the editor the first time
it removes a photo's background and run on the graphics card by `cutout-net.js`
(`cutout-model.js` says which file and checks its SHA-256). The release publishes this folder at
https://rycpot.github.io/extra-guac/models/.

It's U-2-Net's small model, u2netp, from [U-2-Net](https://github.com/xuebinqin/U-2-Net) by Xuebin
Qin, Zichen Zhang, Chenyang Huang, Masood Dehghan, Osmar R. Zaiane and Martin Jagersand, under the
[Apache License 2.0](u2netp.LICENSE). Changed from the original: only the part that makes the
final mask is kept, at a fixed 320 × 320 input, with each convolution's ReLU joined to it, and the
weights stored as 16-bit integers with one scale per output channel (`tools/u2pack.py`). Its
output differs from the original's on about 0.04% of mask pixels.
