# SEO相关

## 如何禁止搜索引擎收录抓取

以下列举了屏蔽主流搜索引擎爬虫（蜘蛛）抓取/索引/收录网页的几种思路。注意：是整站屏蔽，而且是尽可能的屏蔽掉所有主流搜索引擎的爬虫（蜘蛛）。

1、通过 robots.txt 文件屏蔽
可以说 robots.txt 文件是最重要的一种渠道（能和搜索引擎建立直接对话），给出以下建议：
User-agent: Baiduspider
Disallow: /
User-agent: Googlebot
Disallow: /
User-agent: Googlebot-Mobile
Disallow: /
User-agent: Googlebot-Image
Disallow:/
User-agent: Mediapartners-Google
Disallow: /
User-agent: Adsbot-Google
Disallow: /
User-agent:Feedfetcher-Google
Disallow: /
User-agent: Yahoo! Slurp
Disallow: /
User-agent: Yahoo! Slurp China
Disallow: /
User-agent: Yahoo!-AdCrawler
Disallow: /
User-agent: YoudaoBot
Disallow: /
User-agent: Sosospider
Disallow: /
User-agent: Sogou spider
Disallow: /
User-agent: Sogou web spider
Disallow: /
User-agent: MSNBot
Disallow: /
User-agent: ia_archiver
Disallow: /
User-agent: Tomato Bot
Disallow: /
User-agent: *
Disallow: /
2、通过 meta tag 屏蔽
在所有的网页头部文件添加，添加如下语句：
<meta name="robots" content="noindex, nofollow">
3、通过服务器（如：Linux/nginx ）配置文件设置
直接过滤 spider/robots 的IP 段。