# Background

!> The Suprnova application suite is currently in public beta, and comes with no warranty. We strongly encourage caution when trying out Suprnova, as it has not reached `1.0.0` yet.

## Architecture

The Suprnova application framework consists of two main components:

1) [Suprnova CLI](supr.md) - The `supr` command line application, which handles the background tasks essential to managing and working in Suprnova Transcoding Pools.

2) [Suprnova GUI](gui.md) - The Suprnova GUI interface for UWP, which enables easy management and execution of `supr` tasks. This application provides a user-friendly, highly-integrated Suprnova experience, and is strongly recommended to all users of Windows 10.

## Getting Started

### System Requirements

Suprnova GUI requires an up-to-date Windows 10 computer, running a modern i3, i5, i7, or i9 Intel procesor.

### Installation

The Suprnova UWP package contains both the GUI and CLI components of Suprnova, making it the best way to get started.

Our anticipated first release for UWP is Feb, 2019.

The `supr` CLI can be used to perform all necessary tasks, however, without the GUI application, the user will lack Intel Media SDK acceleration, so its use is strongly encouraged. An installation guide for the `supr` CLI application is forthcoming.

## Workflows

Suprnova provides two user workflows:

1) [**Pool Host**](/gui?id=host-view) - Setup a new Suprnova Transcoding Pool on the host system, enabling other users to connect to the Pool and assist in transcoding your video content.

2) **Pool Participant** - Join another individual's Suprnova Transcoding Pool, and assist the **Pool Host** in transcoding the source video content.

### Pool Host

**Pool Hosts** establish a new pool by preparing a source video file and configuring the desired encoding parameters which all **Pool Participants** must target. The Suprnova GUI's Pool Configuration page makes this extremely easy, simplifying the process to one button click.

### Pool Participant

**Pool Participants** join Suprnova Transcoding Pools by providing an encryption key, which is given to them by the **Pool Host**. Once joined, **Participants** wait until new video segments are ready to encode, at which point **Participants** are automatically assigned segments to process. Most participants will find that these processing activities are so miniscule that they make no noticeable impact on system performance.

## Rewards

**Participants** will be rewarded for their encoding efforts by being the first to receive the new transcoded content they helped to process. Most users will find that receipt of the new content is remarkably quick and painless, due to the distributed and decentralized nature of Suprnova Transcoding Pools.

Since all **Participants** are interested in receiving the same video content as you, they each have an incentive to stick around and help to deliver the content that was just transcoded to all other pool participants, not dissimilar to how torrents incentivize participation and sharing.

New kinds of rewards will be introduced in future versions of the Suprnova application framework. Star this repo to track in order to be the first to hear about new Suprnova reward features!
