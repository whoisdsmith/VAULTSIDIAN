# Clip as a Service

---

CLIP-as-service is a low-latency high-scalability service for embedding images and text. It can be easily integrated as a microservice into neural search solutions.

⚡ **Fast**: Serve CLIP models with TensorRT, ONNX runtime and PyTorch w/o JIT with 800QPS<sup>[*]</sup>. Non-blocking duplex streaming on requests and responses, designed for large data and long-running tasks.

🫐 **Elastic**: Horizontally scale up and down multiple CLIP models on single GPU, with automatic load balancing.

🐥 **Easy-to-use**: No learning curve, minimalist design on client and server. Intuitive and consistent API for image and sentence embedding.

👒 **Modern**: Async client support. Easily switch between gRPC, HTTP, WebSocket protocols with TLS and compression.

🍱 **Integration**: Smooth integration with neural search ecosystem including [Jina](https://github.com/jina-ai/jina) and [DocArray](https://github.com/jina-ai/docarray). Build cross-modal and multi-modal solutions in no time.

<sup>[*] with default config (single replica, PyTorch no JIT) on GeForce RTX 3090. </sup>

<!-- end elevator-pitch -->

## Try It!

An always-online server `api.clip.jina.ai` loaded with `ViT-L-14-336::openai` is there for you to play & test.  
Before you start, make sure you have obtained an access token from our [console website](https://console.clip.jina.ai/get_started),  
or via CLI as described in [this guide](https://docs.jina.ai/jina-ai-cloud/login/#create-a-new-pat).

```bash 
jina auth token create <name of PAT> -e <expiration days>
```

Then, you need to configure the access token in the parameter `credential` of the client in python or set it in the HTTP request header `Authorization` as `<your access token>`.

⚠️ Our demo server `demo-cas.jina.ai` is sunset and no longer available after **15th of Sept 2022**.

### Text & Image Embedding

<table>
<tr>
<td> via HTTPS 🔐 </td>
<td> via gRPC 🔐⚡⚡ </td>
</tr>
<tr>
<td>

```bash
curl \
-X POST https://api.clip.jina.ai:8443/post \
-H 'Content-Type: application/json' \
-H 'Authorization: <your access token>' \
-d '{"data":[{"text": "First do it"}, 
    {"text": "then do it right"}, 
    {"text": "then do it better"}, 
    {"uri": "https://picsum.photos/200"}], 
    "execEndpoint":"/"}'
```

</td>
<td>

```python
# pip install clip-client
from clip_client import Client

c = Client(
    'grpcs://api.clip.jina.ai:2096', credential={'Authorization': '<your access token>'}
)

r = c.encode(
    [
        'First do it',
        'then do it right',
        'then do it better',
        'https://picsum.photos/200',
    ]
)
print(r)
```

</td>
</tr>
</table>

### Visual Reasoning

There are four basic visual reasoning skills: object recognition, object counting, color recognition, and spatial relation understanding. Let's try some:

> You need to install [`jq` (a JSON processor)](https://stedolan.github.io/jq/) to prettify the results.

<table>
<tr>
<td> Image </td>
<td> via HTTPS 🔐 </td>
</tr>
<tr>
<td>
<img src="https://picsum.photos/id/1/300/300">
</td>
<td>

```bash
curl \
-X POST https://api.clip.jina.ai:8443/post \
-H 'Content-Type: application/json' \
-H 'Authorization: <your access token>' \
-d '{"data":[{"uri": "https://picsum.photos/id/1/300/300",
"matches": [{"text": "there is a woman in the photo"},
            {"text": "there is a man in the photo"}]}],
            "execEndpoint":"/rank"}' \
| jq ".data[].matches[] | (.text, .scores.clip_score.value)"
```

gives:

```
"there is a woman in the photo"
0.626907229423523
"there is a man in the photo"
0.37309277057647705
```

</td>
</tr>
<tr>
<td>
<img src="https://picsum.photos/id/133/300/300">
</td>
<td>

```bash
curl \
-X POST https://api.clip.jina.ai:8443/post \
-H 'Content-Type: application/json' \
-H 'Authorization: <your access token>' \
-d '{"data":[{"uri": "https://picsum.photos/id/133/300/300",
"matches": [
{"text": "the blue car is on the left, the red car is on the right"},
{"text": "the blue car is on the right, the red car is on the left"},
{"text": "the blue car is on top of the red car"},
{"text": "the blue car is below the red car"}]}],
"execEndpoint":"/rank"}' \
| jq ".data[].matches[] | (.text, .scores.clip_score.value)"
```

gives:

```
"the blue car is on the left, the red car is on the right"
0.5232442617416382
"the blue car is on the right, the red car is on the left"
0.32878655195236206
"the blue car is below the red car"
0.11064132302999496
"the blue car is on top of the red car"
0.03732786327600479
```

</td>
</tr>


<tr>
<td>
<img src="https://picsum.photos/id/102/300/300">
</td>
<td>

```bash
curl \
-X POST https://api.clip.jina.ai:8443/post \
-H 'Content-Type: application/json' \
-H 'Authorization: <your access token>' \
-d '{"data":[{"uri": "https://picsum.photos/id/102/300/300",
"matches": [{"text": "this is a photo of one berry"},
            {"text": "this is a photo of two berries"},
            {"text": "this is a photo of three berries"},
            {"text": "this is a photo of four berries"},
            {"text": "this is a photo of five berries"},
            {"text": "this is a photo of six berries"}]}],
            "execEndpoint":"/rank"}' \
| jq ".data[].matches[] | (.text, .scores.clip_score.value)"
```

gives:

```
"this is a photo of three berries"
0.48507222533226013
"this is a photo of four berries"
0.2377079576253891
"this is a photo of one berry"
0.11304923892021179
"this is a photo of five berries"
0.0731358453631401
"this is a photo of two berries"
0.05045759305357933
"this is a photo of six berries"
0.04057715833187103
```

</td>
</tr>


</table>

## [Documentation](https://clip-as-service.jina.ai)

## Install

CLIP-as-service consists of two Python packages `clip-server` and `clip-client` that can be installed *independently*. Both require Python 3.7+.

### Install Server

<table>
<tr>
<td> Pytorch Runtime ⚡ </td>
<td> ONNX Runtime ⚡⚡</td>
<td> TensorRT Runtime ⚡⚡⚡ </td>
</tr>
<tr>
<td>

```bash
pip install clip-server
```

</td>
<td>

```bash
pip install "clip-server[onnx]"
```

</td>
<td>

```bash
pip install nvidia-pyindex 
pip install "clip-server[tensorrt]"
```

</td>
</tr>
</table>

You can also [host the server on Google Colab](https://clip-as-service.jina.ai/hosting/colab/), leveraging its free GPU/TPU.

### Install Client

```bash
pip install clip-client
```

### Quick Check

You can run a simple connectivity check after install.

<table>
<tr>
<th> C/S </th>
<th> Command </th>
<th> Expect output </th>
</tr>
<tr>
<td>
Server
</td>
<td>

```bash
python -m clip_server
```

</td>
<td>

<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/server-output.svg?raw=true" alt="Expected server output" width="300px">

</td>
</tr>
<tr>
<td>
Client
</td>
<td>

```python
from clip_client import Client

c = Client('grpc://0.0.0.0:23456')
c.profile()
```

</td>
<td>

<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/pyclient-output.svg?raw=true" alt="Expected clip-client output" width="300px">

</td>
</tr>
</table>

You can change `0.0.0.0` to the intranet or public IP address to test the connectivity over private and public network.

## Get Started

### Basic Usage

1. Start the server: `python -m clip_server`. Remember its address and port.
2. Create a client:

   ```python
    from clip_client import Client
   
    c = Client('grpc://0.0.0.0:51000')
    ```

3. To get sentence embedding:

    ```python    
    r = c.encode(['First do it', 'then do it right', 'then do it better'])
    
    print(r.shape)  # [3, 512] 
    ```

4. To get image embedding:

    ```python    
    r = c.encode(['apple.png',  # local image 
                  'https://clip-as-service.jina.ai/_static/favicon.png',  # remote image
                  'data:image/gif;base64,R0lGODlhEAAQAMQAAORHHOVSKudfOulrSOp3WOyDZu6QdvCchPGolfO0o/XBs/fNwfjZ0frl3/zy7////wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH5BAkAABAALAAAAAAQABAAAAVVICSOZGlCQAosJ6mu7fiyZeKqNKToQGDsM8hBADgUXoGAiqhSvp5QAnQKGIgUhwFUYLCVDFCrKUE1lBavAViFIDlTImbKC5Gm2hB0SlBCBMQiB0UjIQA7'])  # in image URI
    
    print(r.shape)  # [3, 512]
    ```

More comprehensive server and client user guides can be found in the [docs](https://clip-as-service.jina.ai/).

### Text-to-image Cross-modal Search in 10 Lines

Let's build a text-to-image search using CLIP-as-service. Namely, a user can input a sentence and the program returns matching images. We'll use the [Totally Looks Like](https://sites.google.com/view/totally-looks-like-dataset) dataset and [DocArray](https://github.com/jina-ai/docarray) package. Note that DocArray is included within `clip-client` as an upstream dependency, so you don't need to install it separately.

#### Load Images

First we load images. You can simply pull them from Jina Cloud:

```python
from docarray import DocumentArray

da = DocumentArray.pull('ttl-original', show_progress=True, local_cache=True)
```

<details>
<summary>or download TTL dataset, unzip, load manually</summary>

Alternatively, you can go to [Totally Looks Like](https://sites.google.com/view/totally-looks-like-dataset) official website, unzip and load images:

```python
from docarray import DocumentArray

da = DocumentArray.from_files(['left/*.jpg', 'right/*.jpg'])
```

</details>

The dataset contains 12,032 images, so it may take a while to pull. Once done, you can visualize it and get the first taste of those images:

```python
da.plot_image_sprites()
```

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/ttl-image-sprites.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="50%">
</p>

#### Encode Images

Start the server with `python -m clip_server`. Let's say it's at `0.0.0.0:51000` with `GRPC` protocol (you will get this information after running the server).

Create a Python client script:

```python
from clip_client import Client

c = Client(server='grpc://0.0.0.0:51000')

da = c.encode(da, show_progress=True)
```

Depending on your GPU and client-server network, it may take a while to embed 12K images. In my case, it took about two minutes.

<details>
<summary>Download the pre-encoded dataset</summary>

If you're impatient or don't have a GPU, waiting can be Hell. In this case, you can simply pull our pre-encoded image dataset:

```python
from docarray import DocumentArray

da = DocumentArray.pull('ttl-embedding', show_progress=True, local_cache=True)
```

</details>

#### Search via Sentence

Let's build a simple prompt to allow a user to type sentence:

```python
while True:
    vec = c.encode([input('sentence> ')])
    r = da.find(query=vec, limit=9)
    r[0].plot_image_sprites()
```

#### Showcase

Now you can input arbitrary English sentences and view the top-9 matching images. Search is fast and instinctive. Let's have some fun:

<table>
<tr>
<th> "a happy potato" </th>
<th> "a super evil AI" </th>
<th> "a guy enjoying his burger" </th>
</tr>
<tr>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/a-happy-potato.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/a-super-evil-AI.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/a-guy-enjoying-his-burger.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
</tr>
</table>


<table>
<tr>
<th> "professor cat is very serious" </th>
<th> "an ego engineer lives with parent" </th>
<th> "there will be no tomorrow so lets eat unhealthy" </th>
</tr>
<tr>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/professor-cat-is-very-serious.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/an-ego-engineer-lives-with-parent.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/there-will-be-no-tomorrow-so-lets-eat-unhealthy.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" width="100%">
</p>

</td>
</tr>
</table>

Let's save the embedding result for our next example:

```python
da.save_binary('ttl-image')
```

### Image-to-text Cross-modal Search in 10 Lines

We can also switch the input and output of the last program to achieve image-to-text search. Precisely, given a query image find the sentence that best describes the image.

Let's use all sentences from the book "Pride and Prejudice".

```python
from docarray import Document, DocumentArray

d = Document(uri='https://www.gutenberg.org/files/1342/1342-0.txt').load_uri_to_text()
da = DocumentArray(
    Document(text=s.strip()) for s in d.text.replace('\r\n', '').split('.') if s.strip()
)
```

Let's look at what we got:

```python
da.summary()
```

```text
            Documents Summary            
                                         
  Length                 6403            
  Homogenous Documents   True            
  Common Attributes      ('id', 'text')  
                                         
                     Attributes Summary                     
                                                            
  Attribute   Data type   #Unique values   Has empty value  
 ────────────────────────────────────────────────────────── 
  id          ('str',)    6403             False            
  text        ('str',)    6030             False            
```

#### Encode Sentences

Now encode these 6,403 sentences, it may take 10 seconds or less depending on your GPU and network:

```python
from clip_client import Client

c = Client('grpc://0.0.0.0:51000')

r = c.encode(da, show_progress=True)
```

<details>
<summary>Download the pre-encoded dataset</summary>

Again, for people who are impatient or don't have a GPU, we have prepared a pre-encoded text dataset:

```python
from docarray import DocumentArray

da = DocumentArray.pull('ttl-textual', show_progress=True, local_cache=True)
```

</details>

#### Search via Image

Let's load our previously stored image embedding, randomly sample 10 image Documents, then find top-1 nearest neighbour of each.

```python
from docarray import DocumentArray

img_da = DocumentArray.load_binary('ttl-image')

for d in img_da.sample(10):
    print(da.find(d.embedding, limit=1)[0].text)
```

#### Showcase

Fun time! Note, unlike the previous example, here the input is an image and the sentence is the output. All sentences come from the book "Pride and Prejudice".

<table>
<tr>
<td>
<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/Besides,-there-was-truth-in-his-looks.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>


</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/Gardiner-smiled.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/what’s-his-name.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/By-tea-time,-however,-the-dose-had-been-enough,-and-Mr.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>

<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/You-do-not-look-well.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
</tr>
<tr>
<td>Besides, there was truth in his looks</td>
<td>Gardiner smiled</td>
<td>what’s his name</td>
<td>By tea time, however, the dose had been enough, and Mr</td>
<td>You do not look well</td>
</tr>
</table>

<table>
<tr>
<td>
<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/“A-gamester!”-she-cried.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>


</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/If-you-mention-my-name-at-the-Bell,-you-will-be-attended-to.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/Never-mind-Miss-Lizzy’s-hair.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/Elizabeth-will-soon-be-the-wife-of-Mr.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>

<td>

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/I-saw-them-the-night-before-last.png?raw=true" alt="Visualization of the image sprite of Totally looks like dataset" height="100px">
</p>

</td>
</tr>
<tr>
<td>“A gamester!” she cried</td>
<td>If you mention my name at the Bell, you will be attended to</td>
<td>Never mind Miss Lizzy’s hair</td>
<td>Elizabeth will soon be the wife of Mr</td>
<td>I saw them the night before last</td>
</tr>
</table>

### Rank Image-text Matches via CLIP Model

From `0.3.0` CLIP-as-service adds a new `/rank` endpoint that re-ranks cross-modal matches according to their joint likelihood in CLIP model. For example, given an image Document with some predefined sentence matches as below:

```python
from clip_client import Client
from docarray import Document

c = Client(server='grpc://0.0.0.0:51000')
r = c.rank(
    [
        Document(
            uri='.github/README-img/rerank.png',
            matches=[
                Document(text=f'a photo of a {p}')
                for p in (
                    'control room',
                    'lecture room',
                    'conference room',
                    'podium indoor',
                    'television studio',
                )
            ],
        )
    ]
)

print(r['@m', ['text', 'scores__clip_score__value']])
```

```text
[['a photo of a television studio', 'a photo of a conference room', 'a photo of a lecture room', 'a photo of a control room', 'a photo of a podium indoor'], 
[0.9920725226402283, 0.006038925610482693, 0.0009973491542041302, 0.00078492151806131, 0.00010626466246321797]]
```

One can see now `a photo of a television studio` is ranked to the top with `clip_score` score at `0.992`. In practice, one can use this endpoint to re-rank the matching result from another search system, for improving the cross-modal search quality.

<table>
<tr>
<td>
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/rerank.png?raw=true" alt="Rerank endpoint image input" height="150px">
</td>
<td>
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/rerank-chart.svg?raw=true" alt="Rerank endpoint output">
</td>
</tr>
</table>

### Rank Text-image Matches via CLIP Model

In the [DALL·E Flow](https://github.com/jina-ai/dalle-flow) project, CLIP is called for ranking the generated results from DALL·E. [It has an Executor wrapped on top of `clip-client`](https://github.com/jina-ai/dalle-flow/blob/main/executors/rerank/executor.py), which calls `.arank()` - the async version of `.rank()`:

```python
from clip_client import Client
from jina import Executor, requests, DocumentArray


class ReRank(Executor):
    def __init__(self, clip_server: str, **kwargs):
        super().__init__(**kwargs)
        self._client = Client(server=clip_server)

    @requests(on='/')
    async def rerank(self, docs: DocumentArray, **kwargs):
        return await self._client.arank(docs)
```

<p align="center">
<img src="https://github.com/jina-ai/clip-as-service/blob/main/.github/README-img/client-dalle.png?raw=true" alt="CLIP-as-service used in DALLE Flow" width="300px">
</p>

Intrigued? That's only scratching the surface of what CLIP-as-service is capable of. [Read our docs to learn more](https://clip-as-service.jina.ai).

---

#AI #stablediffusion #image
