## Dataset Metadata
The following table is necessary for this dataset to be indexed by search
engines such as <a href="https://g.co/datasetsearch">Google Dataset Search</a>.
<div itemscope itemtype="http://schema.org/Dataset">
<table>
  <tr>
    <th>property</th>
    <th>value</th>
  </tr>
  <tr>
    <td>name</td>
    <td itemprop="name">wikisum</td>
  </tr>
  <tr>
    <td>alternateName</td>
    <td itemprop="alternateName">WikisumCommonCrawl</td>
  </tr>
  <tr>
    <td>alternateName</td>
    <td itemprop="alternateName">WikisumWeb</td>
  </tr>
  <tr>
    <td>alternateName</td>
    <td itemprop="alternateName">wkisum_commoncrawl</td>
  </tr>
  <tr>
    <td>alternateName</td>
    <td itemprop="alternateName">wikisum_web</td>
  </tr>
  <tr>
    <td>url</td>
    <td itemprop="url">https://github.com/tensorflow/tensor2tensor/tree/master/tensor2tensor/data_generators/wikisum</td>
  </tr>
  <tr>
    <td>sameAs</td>
    <td itemprop="url">https://github.com/tensorflow/tensor2tensor/tree/master/tensor2tensor/data_generators/wikisum</td>
  </tr>
  <tr>
    <td>description</td>
    <td itemprop="description">The dataset from the
paper [Generating Wikipedia by Summarizing Long
Sequences](https://arxiv.org/abs/1801.10198). The task is to generate a
Wikipedia article based on the contents of the cited references in that article
and the top 10 Google search results for the article's title.

There are 2 sources for the reference URLs used:

1. [CommonCrawl](http://commoncrawl.org/), an open-source crawl of the web. The
   advantage of using CommonCrawl is that the dataset is perfectly reproducible.
   However, there is limited coverage of the reference URLs.
1. Live web fetches. Coverage is considerably increased, but the content is
   subject to change.

The dataset includes:

**URLs:** The dataset contains ~90M URLs total (~2.3M Wikipedia articles, each
with ~40 reference URLs). The URLs in the dataset are available in sharded JSON
files here: `gs://tensor2tensor-data/wikisum/wiki_urls/`.

**Wikipedia Articles:** We have processed the Wikipedia articles slightly to
extract the title, section breaks, and section headings. The processed Wikipedia
content is available in sharded `TFRecord` files containing serialized
`tensorflow.Example` protocol buffers here:
`gs://tensor2tensor-data/wikisum/wiki_content/`. The sharding is determined by a
hash of the Wikpedia article's title. The `Example`s contain features `[url,
title, section_titles, section_texts]`.

**CommonCrawl References Index:** To enable efficiently extracting the reference
URLs from CommonCrawl, we provide a JSON file per CommonCrawl file which maps a
reference URL contained in that CommonCrawl file to a list of shard ids:
`gs://tensor2tensor-data/wikisum/commoncrawl_metadata/`. These shards are the
ones that contain one or more Wikipedia articles that cite this reference. The
scripts in this directory will use this information to efficiently join the
reference with their Wikipedia articles.</td>
  </tr>
  <tr>
    <td>citation</td>
    <td itemprop="citation">https://identifiers.org/arxiv:1801.10198</td>
  </tr>
  <tr>
    <td>provider</td>
    <td>
      <div itemscope itemtype="http://schema.org/Organization" itemprop="provider">
        <table>
          <tr>
            <th>property</th>
            <th>value</th>
          </tr>
          <tr>
            <td>name</td>
            <td itemprop="name">Google</td>
          </tr>
          <tr>
            <td>sameAs</td>
            <td itemprop="sameAs">https://en.wikipedia.org/wiki/Google</td>
          </tr>
        </table>
      </div>
    </td>
  </tr>
</table>
</div>
