# WebflowIndexer

This repository holds the public content index used by Cairn (叠石), a browser extension that shows web pages as a vertical feed. The files here are generated once a day; there is no code in this repository.

这里是“Cairn 叠石”浏览器扩展使用的公开内容索引，每天自动生成一次。

## About the crawler

Requests come with the user agent `WebflowIndexer/0.2 (+https://github.com/jccjd/webflow-index)`.

- It reads RSS/Atom feeds of blogs listed in public directories (Kagi Small Web, a list of Chinese independent blogs, the Travellings and Boyouquan blog rings), Hacker News search results, and Wikipedia's featured and good article lists.
- It obeys `robots.txt`. To stop it, add:

  ```
  User-agent: WebflowIndexer
  Disallow: /
  ```

- It sends at most one request at a time to a site, at least 2 seconds apart, and uses conditional requests, so an unchanged feed costs a `304`.
- The index stores only the title, link, a short excerpt and the image URL your feed already publishes. Readers open your page itself, on your site.

To have your site removed, or for any other question, please [open an issue](https://github.com/jccjd/webflow-index/issues).

## 关于抓取

- 只读公开目录（Kagi Small Web、中文独立博客列表、开往、博友圈）里博客的订阅源、Hacker News 搜索结果、维基百科的典范和优良条目列表。
- 遵守 robots.txt，按上面的写法就能禁止抓取。同一网站同一时间只有一个请求，间隔至少 2 秒。
- 索引里只有标题、链接、摘要和配图地址，读者看的是你网站上的原网页。
- 要求移除或有任何问题，请[提 issue](https://github.com/jccjd/webflow-index/issues)。

## Files

- `manifest.json`: shard counts per language
- `{lang}/{nnn}.json`: shards of about 450 items each
