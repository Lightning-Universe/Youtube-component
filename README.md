> :warning: **EXPERIMENTAL** This is an experimental repo and should be considered as such when using this component.

<!---:lai-name: BigQuery--->

<div align="center">
<img src="static/youtube-downloader-icon.jpeg" width="200px">

```
A Lightning component to download videos from YouTube.
______________________________________________________________________
```

![Tests](https://github.com/PyTorchLightning/LAI-bigquery/actions/workflows/ci-testing.yml/badge.svg)

</div>

### About

This component lets you download videos from YouTube.

### Use the component

To download a video

```python
import lightning as L
from lai_youtubedownloader import VideoDownloader


class YourComponent(L.LightningFlow):
    def __init__(self) -> None:
        super().__init__()
        self.downloader = VideoDownloader()
        self.destination = "<FILEPATH TO SAVE VIDEO TO>"

    def run(self):
        # Download data to filesystem
        self.downloader.download_video(
            link="<URL OF YOUTUBE VIDEO>", filename=self.destination
        )


app = L.LightningApp(YourComponent())
```

### Install

Run the following to install:

```shell
git clone https://github.com/Lightning-AI/LAI-youtube-Component
cd LAI-youtubedownloader
pip install -r requirements.txt
pip install -e .
```

### Tests

To run unit tests locally:

```shell
# From the root level of the package (LAI-youtube)
pip install -r tests/requirements.txt
pytest
```
