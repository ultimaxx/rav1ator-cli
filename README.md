# rAV1ator CLI

(just a lazy fork, don't think this will go anywhere)

An easy-to-use CLI utility for working with Av1an, written in Bash.

rAV1ator CLI is a command-line utility for encoding videos using the Av1an encoding toolkit. It provides an easy-to-use interface for configuring various encoding settings, selecting encoders, and managing the encoding process. The utility is written in Bash and leverages the power of Av1an for efficient AV1 encoding.

```zsh
~ > rav1ator-cli -h
rAV1ator: CLI Edition_ v0.2.4

Usage:
	rav1ator-cli [input] [output] [--offline]

Dependencies (Arch):
	zstd tar ffmpeg python mkvtoolnix-cli vapoursynth gum numactl l-smash vapoursynth-plugin-lsmashsource av1an ffms2

Options: (Currently, only one option is useful at a time)
	-h, --help			Print this help section
	-l, --last-used		Print last used encode settings from history
	-f, --full-history	Print full history from ".rav1ator-cli-history" file
	-b, --binaries		Just install binaries, then exit
	-x, --offline		Don't check for updates.
	-a, --batch			Batch encode. All video files in a directory specified after this flag are encoded.
```

## Features

- **Encoder Selection**: Choose from a variety of encoders including x264, x265, aomenc, SVT-AV1, and rav1e.
- **Interactive Configuration**: Set encoding parameters such as speed presets, CRF/quality values, FFmpeg parameters, and encoder-specific options through an interactive command-line interface.
- **Batch Encoding**: Encode an entire directory of video files with the same settings.
- **Encoding History**: View your encoding history, including the last used settings and the complete history.
- **Resume Encoding**: Resume a previous encoding session, allowing you to continue from where you left off.
- **Binary Management**: Download and install optimized encoder binaries compiled with performance-oriented flags for optimal encoding speed.
- **Update Checking**: Automatically check for updates on every run.
- **Rich Interactivity**: Enjoy a visually appealing experience with spinners, prompts, and dropdown menus.

Overall, it aims to provide an easy way to encode videos on the command line with helpful visual feedback. The interactive prompts help users pick encoding settings without needing deep encoding knowledge.

## Dependencies & Installation

*Note: Full installation instructions are provided on the Codec Wiki on [this page](https://wiki.x266.mov/docs/utilities/rav1ator-cli). These instructions here assume you are on Arch Linux; if you are using anything else, refer to the wiki.*

Installing rAV1ator CLI on its own is as simple as running the following commands:

```bash
curl -sOJ https://raw.githubusercontent.com/ultimaxx/rav1ator-cli/main/rav1ator-cli
chmod +x rav1ator-cli
sudo cp rav1ator-cli /usr/local/bin
```

rAV1ator CLI will not work properly if not installed in `/usr/local/bin`.

After it is properly installed, it will update itself in the future when updates become available.

Dependencies can be installed on Arch by running the following command:

```bash
yay -Syu openssl ffmpeg python mkvtoolnix-cli vapoursynth gum l-smash vapoursynth-plugin-lsmashsource av1an ffms2
```

## Pre-compiled Binary Disclaimer

Binaries installed by rAV1ator CLI are downloaded directly from my repo here. In this repo's commit history, you can see that the commits where I added the ZSTD archives to this repo's `bin/` directory are signed by my GPG key, verifying I made these commits and the binaries in that directory are the ones I intend to ship. The SHA256 hashes that are checked upon the decompression of each binary's respective archive have also been verifiably added by myself, ensuring that the hashes I committed must be identical to the file contents. This means if someone spoofs the URLs you are downloading from, the binary integrity is still checked manually by the script itself.

I strive to provide safe pre-compiled binary installation for everyone. That being said, it is always advisable to be cautious about the use of pre-compiled binaries on your system that are not from trusted sources. I consider myself a trusted source for the reasons above, but if you do not blindly trust my willingness to provide safe binaries forever with no malicious intent, you are entirely justified in your reasoning and you may be better off building from source.

Redistribution of the binaries I have compiled here is fair and just under as it pertains to the terms of the licenses attached to each binary. These can be found in the `legal/` directory that is automatically downloaded alongside the binaries via rAV1ator CLI's binary installation, or within the `bin/` directory of this repo.

## Demos

![rav1ator_cli-demo1](./static/rav1ator_cli_demo1.avif)

![rav1ator_cli-demo2](./static/rav1ator_cli_demo2.avif)

If you want to learn more about AV1 encoding, check out [AV1 Encoding for Dummies](https://wiki.x266.mov/blog/av1-encoding-for-dummies) on the Codec Wiki.

## Contributing

Contributions to rAV1ator CLI are welcome! If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request on the GitHub repository.

## License

rAV1ator CLI is released under the BSD 3-Clause License. See the [LICENSE](LICENSE) file for more information.
