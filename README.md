# 指南 :bookmark:
1) 利用[邊際效益遞減法則]()來防止過度封鎖（例如：使用[合理](https://www.privacyguides.org/en/basics/threat-modeling/)且高品質的[阻擋清單](https://github.com/yokoffing/NextDNS-Config#blocklists-1)；允許大多數的[頂級網域 (TLDs)](https://github.com/yokoffing/NextDNS-Config#block-top-level-domains-tlds-1-2-3-4-5-) 等）。
2) 通過「[長輩測試](https://www.urbandictionary.com/define.php?term=Grandma%20Test)」(Grandma Test)，僅有極少數例外。這些例外情況會在指南中加以說明。

***

## 建立您的帳戶

[在此](https://nextdns.io/?from=xujj63g5)註冊 NextDNS 並支持本頁面！

***

# 安全性 :police_officer:

安全性設定可保護您的資料免受傷害、竊取和未經授權的使用。<sup>*^[這為什麼重要？](https://thenewoil.org/en/guides/prologue/why)*</sup>

## 威脅情資來源 (Threat Intelligence Feeds) <sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/threat-intelligence-feeds.json)</sup></sup>
> [!CAUTION]
> 如果您使用的是[推薦阻擋清單](https://github.com/yokoffing/NextDNS-Config#privacy-lock)以外的清單，請保持啟用此功能 (參見 https://github.com/yokoffing/NextDNS-Config/issues/74 和 https://github.com/yokoffing/NextDNS-Config/issues/86)。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 使用威脅情資來源

## AI 驅動的威脅偵測 (AI-Driven Threat Detection) <sup><sup>[1](https://x.com/NextDNS/status/1440291577713233925)</sup></sup>

NextDNS 將此功能標記為 [beta](https://www.vocabulary.com/dictionary/beta) (測試版)，儘管大多數使用者回報其運作良好。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 AI 驅動的威脅偵測

## Google 安全瀏覽 (Google Safe Browsing) <sup><sup> [1](https://safebrowsing.google.com/safebrowsing/report_general/) [2](https://blog.cryptographyengineering.com/2019/10/13/dear-apple-safe-browsing-might-not-be-that-safe/) [3](https://the8-bit.com/apple-proxies-google-safe-browsing-privacy/) [4](https://github.com/brave/brave-browser/wiki/Deviations-from-Chromium-(features-we-disable-or-remove)#services-we-proxy-through-brave-servers) </sup></sup>
> [!CAUTION]
> Google 安全瀏覽並非設計為 DNS 層級的阻擋器，可能會將合法的 [CNAME 網域](https://en.wikipedia.org/wiki/CNAME_record) 標記為詐騙。NextDNS 可能需要數個月的時間才能移除[誤判](https://csrc.nist.gov/glossary/term/false_positive)。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 Google 安全瀏覽

## 挖礦劫持防護 (Cryptojacking Protection) <sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/cryptojacking.json)</sup></sup>
> [!CAUTION]
> 如果您使用的是[推薦阻擋清單](https://github.com/yokoffing/NextDNS-Config#privacy-lock)以外的清單，請保持啟用此功能 (參見 https://github.com/yokoffing/NextDNS-Config/issues/31)。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用挖礦劫持防護

## DNS 重綁定防護 (DNS Rebinding Protection) <sup><sup>[1](https://help.nextdns.io/t/35hmval/what-is-dns-rebinding-protection) [2](https://www.reddit.com/r/nextdns/comments/t0ne8r/does_dns_rebinding_protection_block_remote_access/?context=3)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg)  啟用 DNS 重綁定防護

## IDN 同型異義字攻擊防護 (IDN Homograph Attacks Protection) <sup><sup>[1](https://web.archive.org/web/20230325073817/https://blog.riotsecurityteam.com/idn-homograph-attacksprevention) [2](https://akamai.com/blog/security/watch-your-step-the-prevalence-of-idn-homograph-attacks)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用同型異義字攻擊防護

## 類似網域搶註防護 (Typosquatting Protection) <sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/typosquatting/protected-domains)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用類似網域搶註防護
## 網域生成演算法 (DGA) 防護
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用 DGA 防護
## 封鎖新註冊網域 (NRDs) <sup><sup>[1](https://boldgrid.com/instagram-influencer-accounts-are-being-hacked-phishing-attacks) </sup></sup>
> [!WARNING]
> 封鎖 NRDs [偶爾](https://www.reddit.com/r/InternetIsBeautiful/comments/w2wdro/comment/iguvg8y/?context=3)可能會導致[誤判](https://csrc.nist.gov/glossary/term/false_positive)。將 NRD 加入允許清單時請謹慎；如果不確定，**切勿**將[敏感資訊](https://egnyte.com/guides/governance/sensitive-information)提供給 NRD。*如果您打算採取「[一勞永逸](https://glosbe.com/en/en/set-and-forget)」的設定方式，請停用此設定。*

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖新註冊網域 (NRDs)

## 封鎖動態 DNS 主機名稱 (Dynamic DNS Hostnames) <sup><sup>[1](https://github.com/nextdns/ddns-domains/blob/main/suffixes) [2](https://x.com/NextDNS/status/1541740963760144386) </sup></sup>
> [!TIP]
> 使用此設定時，動態 DNS (DDNS) 服務仍然可以存取其自己的網站並更新 API。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用封鎖動態 DNS 主機名稱

## 封鎖停放網域 (Parked Domains) <sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/parked-domains-cname)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖停放網域
## 封鎖頂級網域 (TLDs) <sup><sup>[1](https://webtribunal.net/blog/tld-statistics/) [2](https://www.spamhaus.org/reputation-statistics/cctlds/domains/) [3](https://bleepingcomputer.com/news/security/verified-twitter-accounts-hacked-to-send-fake-suspension-notices/) [4](https://github.com/DandelionSprout/adfilt/blob/master/Dandelion%20Sprout's%20Anti-Malware%20List.txt) [5](https://github.com/DandelionSprout/adfilt/issues/659#issuecomment-1284845803) </sup></sup>

> [!IMPORTANT]
> 封鎖 [TLDs](https://www.geeksforgeeks.org/components-of-a-url) 會有同時封鎖惡意網站與合法網站的風險，因為此功能會阻止網站瀏覽和子請求。不過，以下列出的項目應該能在提供對常用濫用 TLD 的防護同時，允許日常的瀏覽行為。

<details><summary>點擊此處查看 TLDs</summary>

```
.autos
.best
.bid
.boats
.boston
.boutique
.charity
.christmas
.dance
.fishing
.hair
.haus
.loan
.loans
.men
.mom
.name
.review
.rip
.skin
.support
.tattoo
.tokyo
.voto
```

</details>

您可以在 [受濫用最多的 TLDs](https://github.com/hagezi/dns-blocklists?tab=readme-ov-file#tlds) 找到更多項目，但您可能偶爾需要將網站加入[允許清單](https://github.com/yokoffing/NextDNS-Config#allowlist-white_check_mark)。*如果您打算採取「[一勞永逸](https://glosbe.com/en/en/set-and-forget)」的設定方式，請跳過此步驟。*

## 封鎖兒童性虐待內容 (CSAM)
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖兒童性虐待內容

***

# 隱私權 :lock:
隱私權功能限制公司可以收集關於您的資料量。

因為隱私是一個[光譜](https://blog.thenewoil.org/the-privacy-myth-binary-vs-spectrum)，您的需求取決於您的[威脅模型](https://thenewoil.org/en/guides/prologue/threat-model/)、興趣和技能組合。<sup>^[*我為什麼要在乎？我又沒做虧心事*](https://medium.com/@FabioAEsteves/i-have-nothing-to-hide-why-should-i-care-about-my-privacy-f488281b8f1d)</sup>

## 阻擋清單 (Blocklists) <sup><sup>[1](https://github.com/nextdns/blocklists/tree/main/blocklists)</sup></sup>

阻擋清單可過濾廣告、[追蹤器](https://www.freecodecamp.org/news/what-you-should-know-about-web-tracking-and-how-it-affects-your-online-privacy-42935355525/)和惡意網站。[開源](https://opensource.com/resources/what-open-source)社群中有數百名志願者為這些清單做出貢獻，他們是使大規模阻擋廣告成為可能的幕後英雄。

我們建議您**移除** [NextDNS Ads & Trackers Blocklist](https://github.com/nextdns/blocklists/blob/main/blocklists/nextdns-recommended.json) 並**新增**[最少](https://www.reddit.com/r/nextdns/comments/1048xeg/do_you_use_nextdns_blocklist_as_the_primary/j33wnz2/?context=3)數量且有用的清單。

### 我應該使用哪個阻擋清單？

一個很好的問題是：「我想在多大程度上處理[誤判](https://csrc.nist.gov/glossary/term/false_positive)帶來的不便？」

以下是根據過去的問題和觀察建議的阻擋清單：

|     **阻擋清單**   |                              **理由**                                             |
|:--------------------:|:--------------------------------------------------------------------------------------:|
| HaGeZi - <br>Multi **NORMAL**<sup>[1](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#multi)</sup> <br>+ <br>OISD<sup>[2](https://www.reddit.com/r/nextdns/comments/1ia9bz0/comment/mdy61v9/)</sup> | 阻擋追蹤器、廣告和惡意軟體請求，且沒有問題（[一勞永逸](https://glosbe.com/en/en/set-and-forget)）。 |
| HaGeZi - <br>Multi **PRO**<sup>[3](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#pro)</sup> | 阻擋更多請求，通常沒有問題（推薦）。 |
| HaGeZi - <br>Multi **PRO++**<sup>[4](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#proplus)</sup> | 阻擋更多請求，但有網站損壞的風險。<br> 需[回報](https://github.com/hagezi/dns-blocklists/issues/new/choose)偶發的網站和應用程式問題。 |

> [!TIP]
> 在不同的 DNS 設定檔上使用不同的阻擋清單（例如：路由器使用 NORMAL，網頁瀏覽器使用 PRO++）。

您也可以查看 Hagezi 自己的[建議](https://github.com/hagezi/dns-blocklists/wiki/FAQ#whatshouldiuse)。

### 為什麼選擇 Hagezi？
[Hagezi](https://github.com/hagezi/dns-blocklists) 阻擋廣告、追蹤器、原生裝置追蹤器和惡意軟體。他維護一個合理的允許清單，能快速處理誤判，並將已知的問題與阻擋清單維護者溝通。Hagezi 使用許多與其他熱門清單（如 OISD 和 1Hosts）相同的原始[來源](https://github.com/hagezi/dns-blocklists/blob/main/sources.md)來建立他的阻擋清單。他還加入了自己獨特的來源，而不僅僅是重新打包其他組合清單。

您可能也想知道為什麼不使用其他清單。這是因為許多清單維護者：
* 不移除[誤判](https://csrc.nist.gov/glossary/term/false_positive)和/或不再活躍 <sup>[1](https://github.com/lightswitch05/hosts/issues/356) [2](https://github.com/EnergizedProtection/block/issues/916)</sup>
* 已經將常見的阻擋清單[聚合](https://www.reddit.com/r/nextdns/comments/ys3s1s/confused_about_blocklists/ivxdcd2/?context=3)到他們自己的清單中（Easylist/Fanboy, AdGuard, Steven Black 等） <sup>[1](https://github.com/badmojr/1Hosts/blob/master/-data/lists/assets.txt) [2](https://oisd.nl/includedlists/big/0) [3](https://github.com/jerryn70/GoodbyeAds/blob/master/Docs/Sources.md) [4](https://github.com/hagezi/dns-blocklists/blob/main/sources.md#sources) </sup>
* 與上述表格組合相比，沒有提供有意義的額外覆蓋範圍

## 原生追蹤防護 (Native Tracking Protection) <sup><sup>[1](https://github.com/nextdns/native-tracking-domains/tree/main/domains)</sup></sup>
> [!CAUTION]
> 如果您使用的是[推薦阻擋清單](https://github.com/yokoffing/NextDNS-Config#privacy-lock)以外的清單，請保持啟用此功能 (參見 https://github.com/yokoffing/NextDNS-Config/issues/76)。

如果您決定使用此功能，請新增您使用的所有裝置品牌。

<details>

	Windows
	Apple
	Samsung
	Xiaomi
	Huawei
	Amazon Alexa
	Roku
	Sonos

</details>

## 封鎖偽裝的第三方追蹤器 (Block Disguised Third-Party Trackers) <sup><sup>[1](https://github.com/nextdns/cname-cloaking-blocklist/blob/master/domains) [2](https://www.reddit.com/r/nextdns/comments/10nenu3/disguised_trackers_are_blocked_regardless_of) [3](https://medium.com/nextdns/cname-cloaking-the-dangerous-disguise-of-third-party-trackers-195205dc522a) [4](https://arxiv.org/pdf/2102.09301.pdf) [5](https://tma.ifip.org/2020/wp-content/uploads/sites/9/2020/06/tma2020-camera-paper66.pdf) </sup></sup>
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖偽裝的第三方追蹤器

該網域[清單](https://github.com/nextdns/cname-cloaking-blocklist/blob/master/domains)已經多年未更新，並且它會封鎖一些 **允許聯盟行銷與追蹤連結** 無法解除封鎖的推薦連結網域。NextDNS 預設會封鎖 [CNAME 記錄](https://en.wikipedia.org/wiki/CNAME_record)，即使停用此清單也是如此。

## 允許聯盟行銷與追蹤連結 (Allow Affiliate & Tracking Links) <sup><sup>[1](https://github.com/nextdns/click-tracking-domains) [2](https://x.com/NextDNS/status/1539229377560461312) </sup></sup>
> [!TIP]
> 您的 IP 位址將自動隱藏（透過 [TCP](https://educba.com/what-is-tcp-ip) [代理](https://en.wikipedia.org/wiki/Proxy_server#/media/File:Proxy_concept_en.svg)）以保護您的隱私。<p>

> [!WARNING]
> 停用此設定會導致某些電子郵件連結無法正確開啟。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 允許聯盟行銷與追蹤連結

***

# 家長監護 :family_man_woman_boy:
## YouTube 嚴格篩選模式
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 強制 YouTube 嚴格篩選模式
## 封鎖繞過方法 (Block Bypass Methods) <sup><sup>[1](https://github.com/nextdns/dns-bypass-methods)</sup></sup>
封鎖可用於繞過 NextDNS 過濾的工具，例如 VPN、代理伺服器、Tor 軟體和加密 DNS 服務。
> [!CAUTION]
> 啟用此設定會導致意想不到的行為。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖繞過方法

***

# 拒絕清單 (Denylist) :no_entry:

拒絕清單項目將永遠被封鎖。這些項目可以進一步強化某些設定檔，同時不干擾日常瀏覽。

### iCloud 私密轉送 (Private Relay)

[iCloud 私密轉送](https://support.apple.com/zh-tw/102602) 可以覆蓋裝置上的 DNS 設定，導致 NextDNS 無法提供保護。

某些 DoH 供應商會自動封鎖此功能。

	mask.icloud.com	

> [!CAUTION]
> 下方的網域可能會導致 Apple 郵件用戶端無法載入外部圖片。除非您執行非常積極的設定檔，否則不需要這些。

以及可能的：

  	apple-relay.cloudflare.com
    apple-relay.fastly-edge.com
	doh.dns.apple.com
	doh.dns.apple.com.v.aaplimg.com
    mask-api.icloud.com
    mask-h2.icloud.com
    mask-canary.icloud.com
    mask.apple-dns.net

***

# 允許清單 (Allowlist) :white_check_mark:

允許清單項目將永遠解析。積極的 DNS 設定檔可能需要這些項目來放寬規則。

### NextDNS

允許 NextDNS 本身，以防過濾清單[出錯](https://help.nextdns.io/t/m1hs207/energized-ultimate-lists-blocking-nextdns)並封鎖您的存取。

	nextdns.io

<details><summary>點擊此處查看更多項目</summary>

### Facebook / Instagram <sup><sup>[1](https://github.com/jerryn70/GoodbyeAds/issues/309)</sup></sup> 

	graph.facebook.com
	graph.instagram.com
	i.instagram.com
	b-graph.facebook.com

如果您仍然遇到問題，請嘗試[這些](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/share/facebook.txt)：
	
	connect.facebook.com
	connect.facebook.net
	graph-fallback.facebook.com
	z-m-graph.facebook.com
	graph-fallback.instagram.com

### Apple 裝置更新 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/536) [2](https://github.com/badmojr/1Hosts/issues/562) [3](https://github.com/nextdns/metadata/pull/1132#issuecomment-1331733770)

一個[已知的追蹤網域](https://gizmodo.com/apple-iphone-analytics-tracking-even-when-off-app-store-1849757558)，但它是裝置更新所需的。

	xp.apple.com

### Apple iMessage GIFs <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/560)</sup></sup> / Spotlight 搜尋 <sup><sup>[2](https://github.com/badmojr/1Hosts/issues/562)</sup></sup> 

	smoot.apple.com

### Apple Store <sup><sup>[1](https://www.reddit.com/r/nextdns/comments/xx4cwn/solutionapple_store_connection_issues)</sup></sup> 

	amp-api-edge.apps.apple.com
	amp-api-search-edge.apps.apple.com

### Windows

使用 NextDNS 的 [原生追蹤](https://github.com/yokoffing/NextDNS-Config#native-tracking-protection-1) 清單 (Windows) 時，此[請求](https://oisd.nl/excludes.php?w=settings-win.data.microsoft.com)會被封鎖

	settings-win.data.microsoft.com

### Xbox 成就

	v10.events.data.microsoft.com
	v20.events.data.microsoft.com

### Xiaomi 裝置更新

	update.intl.miui.com

### Xiaomi USB 偵錯 (安全性設定)

	srv.sec.intl.miui.com

### Google Nest 使用量指標 <sup><sup>[1](https://www.reddit.com/r/nextdns/comments/yzvnuw/nest_usage_metrics_being_blocked)</sup></sup> 

	logsink.devices.nest.com

### Yahoo Mail <sup><sup>[1](https://github.com/hagezi/dns-blocklists/issues/269)</sup></sup>

	consent.yahoo.com
	guce.oath.com
	pr.comet.yahoo.com

### [Spectrum](https://spectrum.net) 登入 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/640)</sup></sup>

	pov.spectrum.net

### Zoom <sup><sup>[1](https://oisd.nl/excludes.php?w=log.zoom.us) [2](https://oisd.nl/excludes.php?w=us04logfiles.zoom.us)</sup></sup> 

	logfiles.zoom.us
	us04logfiles.zoom.us
	us04zpns.zoom.us

### YouTube 觀看紀錄

	s.youtube.com

### Hulu <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/762)</sup></sup>

	ads-fa-darwin.hulustream.com

### Epic Games 啟動器 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/643)</sup></sup>

	eulatracking-public-service-prod06.ol.epicgames.com

### NVIDIA GeForce Experience <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/650)</sup></sup>
	
	gfe.nvidia.com
	nvgs.nvidia.cn

### Chick-Fil-A 應用程式 <sup><sup>[1](https://www.reddit.com/r/nextdns/comments/zaqio0/comment/iz7v9di/?utm_source=share&utm_medium=web2x&context=3)</sup></sup>

	tmetrix.my.chick-fil-a.com

### [imgur](https://imgur.com) <sup><sup>[1](https://github.com/lightswitch05/hosts/issues/358) [2](https://www.reddit.com/r/nextdns/comments/t3jmvk/imgur_loads_then_goes_blank_no_matter_which)</sup></sup>

	js.media-lab.ai

### [CBS](https://cbsnews.com/live) 新聞直播 <sup><sup>[1](https://github.com/nextdns/metadata/issues/1030) [2](https://github.com/hagezi/dns-blocklists/issues/422)</sup></sup> 

	doppler-config.cbsivideo.com
	production-cmp.isgprivacy.cbsi.com
	pubads.g.doubleclick.net
	tags.tiqcdn.com 

### [Paramount+](https://www.paramountplus.com/)

Paramount+ 使用某些網域來顯示廣告。必須允許存取這些網域才能讓 Paramount+ 內容載入（即使是對於無廣告方案的觀眾也是如此）。

:warning: 然而，因為許多網站都使用這些網域來投放廣告，允許它們可能會導致您造訪的其他網站顯示更多廣告。

    imasdk.googleapis.com
    pubads.g.doubleclick.net

使用者[回報](https://www.reddit.com/r/nextdns/comments/v84ag6/paramount_plus/)以下網域可能也需要允許：

    cbsaavideo.com
    cbsi.com
    conviva.com
    convivia.com
    demdex.net
    dns-clientinfo.cbsivideo.com
    partnerad.l.doubleclick.net
    saa.cbsi.com
    summerhamster.com (對，真的)
    udm.scorecardresearch.com

### [FiveThirtyEight](https://fivethirtyeight.com) 影片 / [國家地理 (National Geographic)](https://nationalgeographic.com) 網站 <sup><sup>[1](https://github.com/notracking/hosts-blocklists/issues/788)</sup></sup>

	dcf.espn.com

### [Men's Health](https://menshealth.com/nutrition/a40868905/chris-hemsworth-chicken-pasta-bake-recipe-centr) 影片 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/651)</sup></sup>

	glimmer.hearstapps.com

</details>

***

# 設定 :gear:

## 紀錄 (Logs)
**儲存位置** → 瑞士 (Switzerland)

## 封鎖頁面 (Block Page)
> [!CAUTION]
> 啟用此設定可能會導致網站瀏覽問題，如果您的裝置上未安裝 [NextDNS Root CA](https://help.nextdns.io/t/g9hmv0a/how-to-install-and-trust-nextdns-root-ca)。此外，此設定會破壞 [Paypal 2FA](https://github.com/hagezi/dns-blocklists/issues/2335)、[iCloud 私密轉送](https://help.nextdns.io/t/g9hdska)、[Microsoft Teams](https://www.reddit.com/r/nextdns/comments/176u2x6/comment/k4pp3ti/?context=3)、[Yahoo! Mail](https://github.com/hagezi/dns-blocklists/issues/269#issuecomment-1409644343)、NAVER 應用程式、[Hoyolab 應用程式](https://help.nextdns.io/t/g9yxqcd/nextdns-blocking-hoyolab)，以及可能的[銀行應用程式](https://help.nextdns.io/t/83yxjgx/most-common-problem-with-nextdns)。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用封鎖頁面

## 匿名化 EDNS 用戶端子網段 (Anonymized EDNS Client Subnet) <sup><sup>[1](https://help.nextdns.io/t/m1hmv04/what-is-edns-client-subnet-ecs) </sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用匿名化 EDNS 用戶端子網段
## 快取加速 (Cache Boost) <sup><sup>[1](https://www.reddit.com/r/nextdns/comments/girmcf/new_setting_cache_boost/)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用快取加速

## CNAME 扁平化 (CNAME Flattening) <sup><sup>[1](https://medium.com/nextdns/nextdns-added-cname-uncloaking-support-becomes-the-first-cross-platform-solution-to-the-problem-e3f437f84342) [2](https://developers.cloudflare.com/dns/cname-flattening/) [3](https://advancedweb.hu/what-is-cname-flattening-and-how-it-helps-redirecting-the-apex-domain) </sup></sup>
> [!WARNING]
> 啟用此功能可能會破壞與 [Yahoo! Mail](https://github.com/hagezi/dns-blocklists/issues/269#issuecomment-1409644343) 的相容性，並導致某些阻擋清單出現問題。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 CNAME 扁平化

## 繞過年齡驗證 (Bypass Age Verification)
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 繞過年齡驗證

## Web3 <sup><sup> [1](https://x.com/NextDNS/status/1491034351391305731) [2](https://gabygoldberg.notion.site/f7050e62461143d49345e7b46eb5576b)</sup></sup>
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 Web3
<p>
除非您使用加密貨幣相關的東西，否則請保持停用。

***
# 常見問題 (FAQ) :question:

## 我該如何註冊 NextDNS？
點擊[此處](https://nextdns.io/?from=xujj63g5)開始。

## 為什麼我仍然看到廣告？
並非所有廣告都能在 DNS 層級被阻擋。<sup>[1](https://www.reddit.com/r/nextdns/comments/14nsfhv/comment/jq982bi/?context=3) [2](https://www.reddit.com/r/nextdns/comments/13urdda/ads_on_manga_sites/)</sup> 您需要一個[廣告阻擋器](https://github.com/yokoffing/NextDNS-Config#i-need-a-browser-with-ad-blocking-which-one-should-i-choose)來阻擋剩下的部分。

這是因為並非所有廣告都來自第三方網域；有些廣告直接來自您造訪的網站，例如 [YouTube](https://discourse.pi-hole.net/t/how-do-i-block-ads-on-youtube/253/2)。DNS 阻擋器阻止網域的解析，而內容阻擋器過濾頁面內容。點擊[此處](https://github.com/yokoffing/NextDNS-Config/tree/main#i-need-a-browser-with-ad-blocking-which-one-should-i-choose)輕鬆安裝輕量級廣告阻擋器。

## 我需要一個有廣告阻擋功能的瀏覽器。我該選擇哪一個？
選擇瀏覽器就像[選擇初始寶可夢](https://www.youtube.com/watch?v=F_8htiBjTCY)一樣親密，所以這裡有一些注意事項：
* 理論上最好的瀏覽器在實際使用中可能運作不佳。
* 瀏覽器是工具！根據您的需求使用各種瀏覽器。
* 您應該為生活的不同領域（例如：工作、學校、個人）使用各種瀏覽器（或瀏覽器設定檔）。

我們基於有效性、資源效率、功能和易用性的組合，提出了以下建議。

| 作業系統 | 瀏覽器 | 內容阻擋器 |
|---|---|---|
| iOS | [Safari](https://www.privacyguides.org/en/mobile-browsers/#safari) | [wBlock](https://apps.apple.com/us/app/wblock/id6746388723) 或 [AdGuard](https://www.privacyguides.org/en/browser-extensions/?h=adguard#adguard) |
| Android | [Brave](https://www.privacyguides.org/en/mobile-browsers/#brave) | 內建阻擋器 |
| Windows <br> macOS <br> Linux | [Firefox](https://www.mozilla.org/en-US/firefox/new/) (搭配 [Betterfox](https://github.com/yokoffing/Betterfox#betterfox)) <p><p> [Brave](https://www.privacyguides.org/en/desktop-browsers/#brave) | [uBlock Origin](https://addons.mozilla.org/blog/ublock-origin-everything-you-need-to-know-about-the-ad-blocker/) <p><p> 內建阻擋器或 [uBlock Origin](https://addons.mozilla.org/blog/ublock-origin-everything-you-need-to-know-about-the-ad-blocker/) |  |

歸根結底，如果您使用 [NextDNS](https://nextdns.io/?from=xujj63g5) + 任何帶有廣告阻擋器的瀏覽器，您的防護覆蓋範圍將超過大多數人。

## 我應該付費使用 NextDNS 嗎？
考慮到它提供的豐富功能，[NextDNS](https://nextdns.io/?from=xujj63g5) 價格非常實惠，每年僅需 $19.90 美元即可使用無限裝置。如果它能讓我的家人免於惡意事件的侵害，NextDNS 就值回票價了。

## 啟用的功能數量會影響 NextDNS 的速度嗎？<sup>[1](https://github.com/yokoffing/NextDNS-Config/issues/12#issue-1465457977) [2](https://www.reddit.com/r/nextdns/comments/135utai/comment/jilbus8/?=&context=3)</sup>

您開啟的設定數量不會影響您的 DNS 延遲。

## 如果我已經在系統層級使用 NextDNS，還需要在瀏覽器層級設定 DoH 嗎？
除非您為瀏覽器使用單獨的設定檔，否則這[不是必須的](https://www.reddit.com/r/nextdns/comments/yfjvqy/is_it_redundant_to_set_at_doh_at_browserlevel_if/iu3vjzt/?context=3)。但是，我建議無論如何都要[在您的網頁瀏覽器中設定它](https://itechtics.com/dns-over-https/#how-to-enable-or-disable-dns-over-https-in-your-browsers)。

## 我有一個路由器設定檔和一個裝置設定檔。我的裝置會使用哪一個？
裝置將使用由 [NextDNS](https://nextdns.io/?from=xujj63g5) 應用程式或已安裝的 [root CA](https://help.nextdns.io/t/g9hmv0a/how-to-install-and-trust-nextdns-root-ca) 設定的設定檔。但是，如果裝置未配置為使用單獨的設定檔，則它將使用 wifi/路由器設定。<sup>[1](https://www.reddit.com/r/nextdns/comments/yf4hnv/question_about_home_router_and_app_running_in/)</sup>

## 安全性、隱私權和匿名性有什麼區別？
請參閱 [文章](https://thenewoil.org/en/guides/prologue/secprivanon/) | [影片](https://www.youtube.com/watch?v=Wpkh-hfULgE)

## NextDNS 會對我的網際網路服務供應商 (ISP) 隱藏活動嗎？
加密的 DNS 查詢可提升隱私權和安全性。這種加密可阻止您的 ISP 查看您搜尋和造訪的網站。

然而，加密 DNS 並不會對您的 ISP 隱藏網站 IP 位址。雖然您的 ISP 無法看到您想存取的特定網域，但他們可以看到您連線到 Cloudflare 或 AWS 等 DNS 伺服器。如果您反覆傳送資料到某個 IP 位址，您的 ISP 可以猜測您正在造訪該位址的網站。

## 我需要 VPN 嗎？
IVPN [認為](https://www.ivpn.net/blog/why-you-dont-need-a-vpn/) 您只需要在三個理由下使用 VPN。主要是為了：

1. 對網站和點對點網路隱藏您的真實 IP 位址，這可防止 ISP 和行動電信業者追蹤您的線上活動。

2. 在機場、飯店、咖啡館和圖書館等場所的公共 Wi-Fi 網路上防範[中間人攻擊](https://en.wikipedia.org/wiki/Man-in-the-middle_attack)和其他[常見攻擊](https://en.wikipedia.org/wiki/Evil_twin_(wireless_networks))。

3. 繞過審查或地理限制，讓您可以存取被封鎖的網站和內容。

最終，除非您的[威脅模型](https://thenewoil.org/en/guides/prologue/threat-model/)有此需求，否則您不需要 VPN。如果有需求，這裡有來自 [Techlore](https://www.techlore.tech/vpn.html) 和 [Tom Spark Reviews](https://www.vpntierlist.com/vpn-tier-list-2024) 的 VPN 建議。

***
# 相關提及與參考 :books:

### 使用者評論
* 請參閱 [此處](https://socialgrep.com/search?query=yokoffing%2Cnextdns)

### YouTube
* [The ULTIMATE Guide to Mastering NextDNS!](https://www.youtube.com/watch?v=WUG57ynLb8I&t=2230s) | [釐清說明](https://github.com/techlore/channel-content/issues/43) (2023 年 7 月)

### 文章
* [Knot Resolver — with ad blocking](https://blog.cavelab.dev/2022/12/knot-resolver-ad-blocking/) (2022 年 12 月)
* [Privacy Toolkit: NextDNS](https://stephenbolen.com/privacy-toolkit-nextdns/#:~:text=I%20found%20a%20wonderful%20guide%20on%20GitHub%20that%20walks%20through%20the%20optimal%20NextDNS%20configuration) (2022 年 9 月)

### 指南
* [A comprehensive guide to setting up NextDNS](https://itsjake.me/blog/a-comprehensive-guide-to-setting-up-nextdns/) (2023 年 9 月)
* [FMHY: DNS Adblocking](https://github.com/nbats/FMHYedit/blob/main/AdblockVPNGuide.md#-dns-adblocking) → NextDNS → Guide
* [hagezi/dns-blocklists](https://github.com/hagezi/dns-blocklists#department_store-nextdns---limited-freepaid-) → Online DNS Services

### 貢獻
* [Hagezi](https://github.com/hagezi/dns-blocklists/issues?q=author%3Ayokoffing) | [提及](https://github.com/hagezi/dns-blocklists/issues?q=mentions%3Ayokoffing)
* [1Hosts](https://github.com/badmojr/1Hosts/issues?q=author%3Ayokoffing)
* [Easylist](https://github.com/easylist/easylist/issues?q=author%3Ayokoffing)
* [uBlock Origin](https://github.com/uBlockOrigin/uAssets/issues?q=author%3Ayokoffing)
* [AdGuard](https://github.com/AdguardTeam/AdguardFilters/issues?q=author%3Ayokoffing)
