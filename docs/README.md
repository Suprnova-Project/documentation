# Suprnova Documentation

![suprnova](http://lims.littlstar.com/streamData/splash.png "Suprnova Logo")

Suprnova is a revolutionary new P2P (peer-to-peer) video encoding and delivery tool for content creators. It allows content creators to invite their fans to directly participate in the transcoding of new content. This is achieved by segmenting videos into tiny chunks of frames, which then get distributed to all participants in the Suprnova encoding pool to be processed. In exchange for this participation, users are rewarded by being the first to receive access to the new content.

## Features


### Intel Hardware Acceleration

![intel](images/mediasdk.png "Intel Media SDK")

In partnership with Intel, we are proud to offer Suprnova users a highly optimized encoding workflow, provided by Intel's Media SDK toolkit. It takes advantage of hardware instructions on your Intel i3, i5, i7, or i9 processor, which have been designed precisely for the purpose of accelerating transcodes. As a result, Suprnova pools encode video much more efficiently than other modern encoding workflows, and offer performance competitive with modern GPU pipelines - but at a fraction of
the cost!

### Double End-to-End Encrypted Connections

Suprnova utilizes the same handshake protocol as the secure chat app, Signal, and implements stream encryption via libsodium's `secretstream`. It further encrypts each socket connection via the `blake2b` encryption algorithm, providing users with peace of mind that their valuable video assets will remain in the proper hands.
