# 指南 :bookmark:
1) 運用[邊際效益遞減法則]()避免過度封鎖（例如：選用[合理](https://www.privacyguides.org/en/basics/threat-modeling/)且高品質的[封鎖清單](https://github.com/yokoffing/NextDNS-Config#blocklists-1)，並允許大多數[頂級網域（TLDs）](https://github.com/yokoffing/NextDNS-Config#block-top-level-domains-tlds-1-2-3-4-5-)等）。
2) 除少數例外情況外，應能通過「[長輩測試](https://www.urbandictionary.com/define.php?term=Grandma%20Test)」（Grandma Test）。這些例外情況都會在本指南中特別說明。

***

## 建立帳戶

歡迎點擊[此處](https://nextdns.io/?from=xujj63g5)註冊 NextDNS，並支持本頁面！

***

# 安全性 :police_officer:

安全性設定能保護您的資料免於受損、竊取與未經授權的使用。<sup>*^[這為什麼重要？](https://thenewoil.org/en/guides/prologue/why)*</sup>

## 威脅情資來源（Threat Intelligence Feeds）<sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/threat-intelligence-feeds.json)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 使用威脅情資來源

## AI 驅動威脅偵測（AI-Driven Threat Detection）<sup><sup>[1](https://x.com/NextDNS/status/1440291577713233925)</sup></sup>
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 AI 驅動威脅偵測

## Google 安全瀏覽（Google Safe Browsing）<sup><sup> [1](https://safebrowsing.google.com/safebrowsing/report_general/) [2](https://blog.cryptographyengineering.com/2019/10/13/dear-apple-safe-browsing-might-not-be-that-safe/) [3](https://the8-bit.com/apple-proxies-google-safe-browsing-privacy/) [4](https://github.com/brave/brave-browser/wiki/Deviations-from-Chromium-(features-we-disable-or-remove)#services-we-proxy-through-brave-servers) </sup></sup>
> [!CAUTION]
> Google 安全瀏覽原本並非針對 DNS 層級封鎖而設計，因此可能會將合法的 [CNAME 網域](https://en.wikipedia.org/wiki/CNAME_record)誤判為詐騙網站。此外，NextDNS 往往需要數個月才能解除[誤判](https://csrc.nist.gov/glossary/term/false_positive)。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 Google 安全瀏覽

## 新註冊網域（Newly Registered Domains, NRDs）<sup><sup>[1](https://boldgrid.com/instagram-influencer-accounts-are-being-hacked-phishing-attacks) </sup></sup>
> [!WARNING]
> 封鎖新註冊網域（NRDs）[偶爾](https://www.reddit.com/r/InternetIsBeautiful/comments/w2wdro/comment/iguvg8y/?context=3)會造成[誤判](https://csrc.nist.gov/glossary/term/false_positive)。將 NRD 加入允許清單時請務必謹慎；一旦加入，**切勿**向該 NRD 提供任何[敏感資訊](https://egnyte.com/guides/governance/sensitive-information)。*若您打算採取「[一勞永逸](https://glosbe.com/en/en/set-and-forget)」的設定方式，請停用此設定。*

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖新註冊網域

## 新啟用網域（Newly Active Domains）
> [!NOTE]
> 此功能常會將流量較低但並非惡意的網頁標示為威脅（[誤判](https://csrc.nist.gov/glossary/term/false_positive)）。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖新啟用網域

## 免費託管網域（Free Hosting Domains）
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖免費託管網域

## 動態 DNS 主機名稱（Dynamic DNS Hostnames）<sup><sup>[1](https://github.com/nextdns/ddns-domains/blob/main/suffixes) [2](https://x.com/NextDNS/status/1541740963760144386) </sup></sup>
> [!TIP]
> 啟用此設定後，動態 DNS（DDNS）服務仍可正常存取自家網站並呼叫更新 API。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖動態 DNS 主機名稱

## 通道端點（Tunneling Endpoints）
> [!WARNING]
> 可能會影響開發人員工作流程、網站託管或遠端家用伺服器連線。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖通道端點

## 住宅網路託管（Residential Hosting）
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖住宅網路託管

## 不受信任的憑證（Untrusted Certificates）
> [!NOTE]
> 憑證通常由網頁瀏覽器負責處理，但您仍可嘗試啟用此功能。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖不受信任的憑證

## 資料投遞服務（Data Drop Services）
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖資料投遞服務

## DNS 酬載傳遞（DNS Payload Delivery）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 阻斷 DNS 酬載傳遞

## 區域網路位址（Local Network Addresses）<sup><sup>[1](https://help.nextdns.io/t/35hmval/what-is-dns-rebinding-protection) [2](https://www.reddit.com/r/nextdns/comments/t0ne8r/does_dns_rebinding_protection_block_remote_access/?context=3)</sup></sup>
亦稱 DNS 重綁定防護（DNS Rebinding Protection）

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖區域網路位址

## 加密貨幣挖礦（Cryptocurrency Mining）<sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/cryptojacking.json)</sup></sup>
> [!CAUTION]
> 若您使用的是[推薦封鎖清單](https://github.com/yokoffing/NextDNS-Config#privacy-lock)以外的清單，請保持啟用此功能（詳見 <https://github.com/yokoffing/NextDNS-Config/issues/31>）。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖加密貨幣挖礦

## 去中心化網路閘道（Decentralized Web Gateways）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖去中心化網路閘道

## 停放網域（Parked Domains）<sup><sup>[1](https://github.com/nextdns/metadata/blob/6f9b6cd0670e7e31ad2ca716742088c2fc0616c2/security/parked-domains-cname)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖停放網域

## 高風險頂級網域（High-Risk TLDs）
 *若您打算採取「[一勞永逸](https://glosbe.com/en/en/set-and-forget)」的設定方式，請跳過此步驟。*
 
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖高風險頂級網域

## 網域生成演算法（Domain Generation Algorithms）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖 DGA 網域

## 頂級網域（Top-Level Domains, TLDs）<sup><sup>[1](https://webtribunal.net/blog/tld-statistics/) [2](https://www.spamhaus.org/reputation-statistics/cctlds/domains/) [3](https://bleepingcomputer.com/news/security/verified-twitter-accounts-hacked-to-send-fake-suspension-notices/) [4](https://github.com/DandelionSprout/adfilt/blob/master/Dandelion%20Sprout's%20Anti-Malware%20List.txt) [5](https://github.com/DandelionSprout/adfilt/issues/659#issuecomment-1284845803) </sup></sup>

> [!IMPORTANT]
> 由於這項功能會同時攔截網頁瀏覽與子請求，封鎖 [TLDs](https://www.geeksforgeeks.org/components-of-a-url) 時可能會將合法網站與惡意網站一併封鎖。不過，下方列出的清單應能在防範常見濫用 TLD 的同時，維持日常正常瀏覽。

<details><summary>點擊檢視 TLDs 清單</summary>

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

您可以在[最常遭濫用的 TLDs](https://github.com/hagezi/dns-blocklists?tab=readme-ov-file#tlds) 中找到更多項目，但日後可能偶爾需要將網站加入[允許清單](https://github.com/yokoffing/NextDNS-Config#allowlist-white_check_mark)。*若您打算採取「[一勞永逸](https://glosbe.com/en/en/set-and-forget)」的設定方式，請跳過此步驟。*

## 封鎖兒童性虐待內容（Child Sexual Abuse Material）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖兒童性虐待內容

***

# 隱私權 :lock:
隱私權功能可限制各家公司能蒐集到的個人資料量。

由於隱私是一種[光譜](https://blog.thenewoil.org/the-privacy-myth-binary-vs-spectrum)，您的實際需求取決於自身的[威脅模型](https://thenewoil.org/en/guides/prologue/threat-model/)、關注程度與技術能力。<sup>^[*我為什麼要在乎？我又沒什麼好隱藏的*](https://medium.com/@FabioAEsteves/i-have-nothing-to-hide-why-should-i-care-about-my-privacy-f488281b8f1d)</sup>

## 封鎖清單（Blocklists）<sup><sup>[1](https://github.com/nextdns/blocklists/tree/main/blocklists)</sup></sup>

封鎖清單能過濾廣告、[追蹤器](https://www.freecodecamp.org/news/what-you-should-know-about-web-tracking-and-how-it-affects-your-online-privacy-42935355525/)與惡意網站。[開源](https://opensource.com/resources/what-open-source)社群中有數百位志願者維護這些清單，正是這群幕後功臣讓大規模廣告封鎖得以實現。

我們建議您**刪除** [NextDNS Ads & Trackers Blocklist](https://github.com/nextdns/blocklists/blob/main/blocklists/nextdns-recommended.json)，並只**新增**[最少數量](https://www.reddit.com/r/nextdns/comments/1048xeg/do_you_use_nextdns_blocklist_as_the_primary/j33wnz2/?context=3)但實用的清單。

### 我該使用哪個封鎖清單？

您不妨先問自己一個關鍵問題：「我願意花多少心力處理[誤判](https://csrc.nist.gov/glossary/term/false_positive)帶來的不便？」

以下依據過往問題與長期觀察，整理出建議採用的封鎖清單：

|     **封鎖清單**   |                              **選擇理由**                                             |
|:--------------------:|:--------------------------------------------------------------------------------------:|
| HaGeZi - <br>Multi **NORMAL**<sup>[1](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#multi)</sup> <br>+ <br>OISD<sup>[2](https://www.reddit.com/r/nextdns/comments/1ia9bz0/comment/mdy61v9/)</sup> | 封鎖追蹤器、廣告與惡意軟體請求且幾乎不出問題（[一勞永逸](https://glosbe.com/en/en/set-and-forget)）。 |
| HaGeZi - <br>Multi **PRO**<sup>[3](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#pro)</sup> | 封鎖更多請求，通常不會造成使用問題（推薦）。 |
| HaGeZi - <br>Multi **PRO++**<sup>[4](https://github.com/hagezi/dns-blocklists/blob/main/statistics.md#proplus)</sup> | 封鎖更多請求，但有網站功能異常的風險。<br> 若遇網站或應用程式偶發異常，需自行[回報問題](https://github.com/hagezi/dns-blocklists/issues/new/choose)。 |

> [!TIP]
> 建議針對不同的 DNS 設定檔套用不同清單（例如：路由器採用 NORMAL，網頁瀏覽器則採用 PRO++）。

您也可以參考 Hagezi 本人撰寫的[選擇建議](https://github.com/hagezi/dns-blocklists/wiki/FAQ#whatshouldiuse)。

### 為什麼選擇 Hagezi？
[Hagezi](https://github.com/hagezi/dns-blocklists) 能有效封鎖廣告、追蹤器、裝置原生追蹤器與惡意軟體。他維護了一套合理的允許清單，處理誤判的速度極快，也會主動向其他清單維護者回報已知問題。Hagezi 的封鎖清單與 OISD、1Hosts 等熱門清單同樣取自許多原始[來源](https://github.com/hagezi/dns-blocklists/blob/main/sources.md)，同時他也加入了自己獨有的來源，而不只是單純把別人的綜合清單重新打包。

您或許會好奇為何不採用其他清單。這是因為許多清單維護者：
* 不願排除[誤判](https://csrc.nist.gov/glossary/term/false_positive)，或已停止維護更新 <sup>[1](https://github.com/lightswitch05/hosts/issues/356) [2](https://github.com/EnergizedProtection/block/issues/916)</sup>
* 早已將常見封鎖清單（如 Easylist/Fanboy、AdGuard、Steven Black 等）[整合](https://www.reddit.com/r/nextdns/comments/ys3s1s/confused_about_blocklists/ivxdcd2/?context=3)進自家清單中 <sup>[1](https://github.com/badmojr/1Hosts/blob/master/-data/lists/assets.txt) [2](https://oisd.nl/includedlists/big/0) [3](https://github.com/jerryn70/GoodbyeAds/blob/master/Docs/Sources.md) [4](https://github.com/hagezi/dns-blocklists/blob/main/sources.md#sources) </sup>
* 與上表建議的組合相比，無法提供有意義的額外防護範圍

## 原生追蹤防護（Native Tracking Protection）<sup><sup>[1](https://github.com/nextdns/native-tracking-domains/tree/main/domains)</sup></sup>
> [!CAUTION]
> 若您使用的是[推薦封鎖清單](https://github.com/yokoffing/NextDNS-Config#privacy-lock)以外的清單，請保持啟用此功能（詳見 <https://github.com/yokoffing/NextDNS-Config/issues/76>）。

若您決定使用此功能，請將您所持有的所有裝置品牌都加入清單中。

<details>

	Windows
	Apple
	Samsung
	Xiaomi
	Huawei
	Amazon Alexa
	Roku
	Sonos
	LG

</details>

## 封鎖輪替廣告網域（Block Rotating Ad Domains）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 封鎖輪替廣告網域

## 封鎖偽裝的第三方追蹤器（Block Disguised Third-Party Trackers）<sup><sup>[1](https://github.com/nextdns/cname-cloaking-blocklist/blob/master/domains) [2](https://www.reddit.com/r/nextdns/comments/10nenu3/disguised_trackers_are_blocked_regardless_of) [3](https://medium.com/nextdns/cname-cloaking-the-dangerous-disguise-of-third-party-trackers-195205dc522a) [4](https://arxiv.org/pdf/2102.09301.pdf) [5](https://tma.ifip.org/2020/wp-content/uploads/sites/9/2020/06/tma2020-camera-paper66.pdf) </sup></sup>
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖偽裝的第三方追蹤器

這份清單會封鎖部分「**允許追蹤連結**」無法解除封鎖的推薦連結網域。即使停用此清單，NextDNS 預設仍會封鎖 [CNAME 記錄](https://en.wikipedia.org/wiki/CNAME_record)。

## 允許追蹤連結（Allow Tracking Links）<sup><sup>[1](https://github.com/nextdns/click-tracking-domains) [2](https://x.com/NextDNS/status/1539229377560461312) </sup></sup>
> [!TIP]
> 系統會透過 [TCP](https://educba.com/what-is-tcp-ip) [代理](https://en.wikipedia.org/wiki/Proxy_server#/media/File:Proxy_concept_en.svg)自動隱藏您的 IP 位址，以保障您的隱私。<p>

> [!WARNING]
> 停用此設定會導致部分電子郵件中的連結無法正常開啟。

![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 允許追蹤連結

***

# 家長監護 :family_man_woman_boy:
## YouTube 嚴格篩選模式（YouTube Restricted Mode）
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 強制啟用 YouTube 嚴格篩選模式

## 封鎖繞過方法（Block Bypass Methods）<sup><sup>[1](https://github.com/nextdns/dns-bypass-methods)</sup></sup>
封鎖可用來繞過 NextDNS 過濾機制的工具，例如 VPN、代理伺服器、Tor 軟體與加密 DNS 服務。
> [!CAUTION]
> 啟用此設定會引發非預期的行為。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 封鎖繞過方法

***

# 拒絕清單 :no_entry:

拒絕清單中的項目一律會遭到封鎖。這些網域可進一步強化特定設定檔的防護，同時不影響日常網頁瀏覽。

### iCloud 私密轉送（iCloud Private Relay）

[iCloud 私密轉送](https://support.apple.com/en-us/102602)會覆寫裝置上的 DNS 設定，導致 NextDNS 無法發揮防護作用。

部分 DoH 供應商會自動封鎖此功能。

	mask.icloud.com	

> [!CAUTION]
> 下方網域可能會導致 Apple 郵件用戶端無法載入外部圖片。除非您使用極度嚴格的設定檔，否則無須加入這些項目。

其他可考慮封鎖的網域：

  	apple-relay.cloudflare.com
    apple-relay.fastly-edge.com
	doh.dns.apple.com
	doh.dns.apple.com.v.aaplimg.com
    mask-api.icloud.com
    mask-h2.icloud.com
    mask-canary.icloud.com
    mask.apple-dns.net

***

# 允許清單 :white_check_mark:

允許清單中的項目一律會正常解析。若您採用較嚴格的 DNS 設定檔，可能需要透過這些項目放寬部分規則。

### NextDNS

請先允許 NextDNS 本身，以免過濾清單[出錯](https://help.nextdns.io/t/m1hs207/energized-ultimate-lists-blocking-nextdns)而誤鎖您對 NextDNS 的存取權限。

	nextdns.io

<details><summary>點擊此處查看更多項目</summary>

### Facebook / Instagram <sup><sup>[1](https://github.com/jerryn70/GoodbyeAds/issues/309)</sup></sup> 

	graph.facebook.com
	graph.instagram.com
	i.instagram.com
	b-graph.facebook.com

若問題仍未解決，請嘗試加入[這些網域](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/share/facebook.txt)：
	
	connect.facebook.com
	connect.facebook.net
	graph-fallback.facebook.com
	z-m-graph.facebook.com
	graph-fallback.instagram.com

### Apple 裝置更新 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/536) [2](https://github.com/badmojr/1Hosts/issues/562) [3](https://github.com/nextdns/metadata/pull/1132#issuecomment-1331733770)

雖然這是[已知的追蹤網域](https://gizmodo.com/apple-iphone-analytics-tracking-even-when-off-app-store-1849757558)，但裝置更新必須仰賴此網域才能運作。

	xp.apple.com

### Apple iMessage GIFs <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/560)</sup></sup> / Spotlight 搜尋 <sup><sup>[2](https://github.com/badmojr/1Hosts/issues/562)</sup></sup> 

	smoot.apple.com

### Apple Store <sup><sup>[1](https://www.reddit.com/r/nextdns/comments/xx4cwn/solutionapple_store_connection_issues)</sup></sup> 

	amp-api-edge.apps.apple.com
	amp-api-search-edge.apps.apple.com

### Windows

使用 NextDNS 的[原生追蹤](https://github.com/yokoffing/NextDNS-Config#native-tracking-protection-1)清單（Windows）時，此[請求](https://oisd.nl/excludes.php?w=settings-win.data.microsoft.com)會遭到封鎖

	settings-win.data.microsoft.com

### Xbox 成就

	v10.events.data.microsoft.com
	v20.events.data.microsoft.com

### 小米裝置更新

	update.intl.miui.com

### 小米 USB 偵錯（安全性設定）

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

Paramount+ 會透過特定網域顯示廣告。即使您訂閱的是無廣告方案，也必須允許存取這些網域，才能讓 Paramount+ 內容順利載入。

:warning: 不過，由於許多網站也使用這些網域投放廣告，允許它們可能會讓您在瀏覽其他網站時看到更多廣告。

    imasdk.googleapis.com
    pubads.g.doubleclick.net

使用者曾[回報](https://www.reddit.com/r/nextdns/comments/v84ag6/paramount_plus/)下列網域可能也需一併允許：

    cbsaavideo.com
    cbsi.com
    conviva.com
    convivia.com
    demdex.net
    dns-clientinfo.cbsivideo.com
    partnerad.l.doubleclick.net
    saa.cbsi.com
    summerhamster.com (沒錯，就是這個)
    udm.scorecardresearch.com

### [FiveThirtyEight](https://fivethirtyeight.com) 影片 / [國家地理（National Geographic）](https://nationalgeographic.com)網站 <sup><sup>[1](https://github.com/notracking/hosts-blocklists/issues/788)</sup></sup>

	dcf.espn.com

### [Men's Health](https://menshealth.com/nutrition/a40868905/chris-hemsworth-chicken-pasta-bake-recipe-centr) 影片 <sup><sup>[1](https://github.com/badmojr/1Hosts/issues/651)</sup></sup>

	glimmer.hearstapps.com

</details>

***

# 設定 :gear:

## 紀錄（Logs）
**儲存位置** → 瑞士（Switzerland）

## 封鎖頁面（Block Page）
> [!CAUTION]
> 若您的裝置尚未安裝 [NextDNS 根憑證授權單位（Root CA）](https://help.nextdns.io/t/g9hmv0a/how-to-install-and-trust-nextdns-root-ca)，啟用此設定可能會導致網頁瀏覽異常。此外，這項設定還會影響 [Paypal 2FA](https://github.com/hagezi/dns-blocklists/issues/2335)、[iCloud 私密轉送](https://help.nextdns.io/t/g9hdska)、[Microsoft Teams](https://www.reddit.com/r/nextdns/comments/176u2x6/comment/k4pp3ti/?context=3)、[Yahoo! Mail](https://github.com/hagezi/dns-blocklists/issues/269#issuecomment-1409644343)、NAVER 應用程式、[Hoyolab 應用程式](https://help.nextdns.io/t/g9yxqcd/nextdns-blocking-hoyolab)，以及部分[銀行應用程式](https://help.nextdns.io/t/83yxjgx/most-common-problem-with-nextdns)的正常運作。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用封鎖頁面

## 匿名化 EDNS 用戶端子網段（Anonymized EDNS Client Subnet）<sup><sup>[1](https://help.nextdns.io/t/m1hmv04/what-is-edns-client-subnet-ecs) </sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用匿名化 EDNS 用戶端子網段

## 快取加速（Cache Boost）<sup><sup>[1](https://www.reddit.com/r/nextdns/comments/girmcf/new_setting_cache_boost/)</sup></sup>
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 啟用快取加速

## CNAME 扁平化（CNAME Flattening）<sup><sup>[1](https://medium.com/nextdns/nextdns-added-cname-uncloaking-support-becomes-the-first-cross-platform-solution-to-the-problem-e3f437f84342) [2](https://developers.cloudflare.com/dns/cname-flattening/) [3](https://advancedweb.hu/what-is-cname-flattening-and-how-it-helps-redirecting-the-apex-domain) </sup></sup>
> [!WARNING]
> 啟用此功能可能會破壞與 [Yahoo! Mail](https://github.com/hagezi/dns-blocklists/issues/269#issuecomment-1409644343) 的相容性，並導致部分封鎖清單運作異常。

![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 CNAME 扁平化

## 繞過年齡驗證（Bypass Age Verification）
![已啟用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/enabled.svg) 繞過年齡驗證

## Web3 <sup><sup> [1](https://x.com/NextDNS/status/1491034351391305731) [2](https://gabygoldberg.notion.site/f7050e62461143d49345e7b46eb5576b)</sup></sup>
![已停用](https://raw.githubusercontent.com/yokoffing/NextDNS-Config/main/icons/disabled.svg) 啟用 Web3
<p>
除非您有使用加密貨幣相關服務，否則請保持停用。

***
# 常見問題（FAQ）:question:

## 我該如何註冊 NextDNS？
點擊[此處](https://nextdns.io/?from=xujj63g5)即可開始註冊。

## 為什麼我還是看得到廣告？
並非所有廣告都能在 DNS 層級就加以封鎖。<sup>[1](https://www.reddit.com/r/nextdns/comments/14nsfhv/comment/jq982bi/?context=3) [2](https://www.reddit.com/r/nextdns/comments/13urdda/ads_on_manga_sites/)</sup> 您仍需要搭配[廣告封鎖器](https://github.com/yokoffing/NextDNS-Config#i-need-a-browser-with-ad-blocking-which-one-should-i-choose)，才能攔截漏網之魚。

這是因為並非所有廣告都來自第三方網域；部分廣告（例如 [YouTube](https://discourse.pi-hole.net/t/how-do-i-block-ads-on-youtube/253/2)）會直接從您造訪的網站本身載入。DNS 封鎖器負責攔截網域解析，而內容封鎖器則負責過濾網頁內容。點擊[此處](https://github.com/yokoffing/NextDNS-Config/tree/main#i-need-a-browser-with-ad-blocking-which-one-should-i-choose)即可輕鬆安裝輕量級廣告封鎖器。

## 我需要具備廣告封鎖功能的瀏覽器，該選哪一款？
挑選瀏覽器就像[選擇初始寶可夢](https://www.youtube.com/watch?v=F_8htiBjTCY)一樣講究契合度，以下先提醒幾個要點：
* 紙上規格最強的瀏覽器，在實際日常使用中未必順手。
* 瀏覽器只是工具！請依照實際需求搭配不同瀏覽器使用。
* 建議為不同的生活情境（例如：工作、學校、個人）區分使用不同的瀏覽器（或瀏覽器設定檔）。

我們綜合評估了封鎖效果、資源效率、功能與易用性，整理出以下建議：

| 作業系統 | 瀏覽器 | 內容封鎖器 |
|---|---|---|
| iOS | [Safari](https://www.privacyguides.org/en/mobile-browsers/#safari) | [wBlock](https://apps.apple.com/us/app/wblock/id6746388723)、[uBlock Origin Lite](https://apps.apple.com/us/app/ublock-origin-lite/id6745342698) 或 [AdGuard](https://www.privacyguides.org/en/browser-extensions/?h=adguard#adguard) |
| Android | [Brave](https://www.privacyguides.org/en/mobile-browsers/#brave) | 內建封鎖器 |
| Windows <br> macOS <br> Linux | [Firefox](https://www.mozilla.org/en-US/firefox/new/)（搭配 [Betterfox](https://github.com/yokoffing/Betterfox#betterfox)）<p><p> [Brave](https://www.privacyguides.org/en/desktop-browsers/#brave) <p><p> [Helium](https://helium.computer/) | [uBlock Origin](https://addons.mozilla.org/blog/ublock-origin-everything-you-need-to-know-about-the-ad-blocker/) <p><p> 內建封鎖器或 [uBlock Origin](https://addons.mozilla.org/blog/ublock-origin-everything-you-need-to-know-about-the-ad-blocker/) |

總而言之，只要您結合 [NextDNS](https://nextdns.io/?from=xujj63g5) 與任何搭載廣告封鎖器的瀏覽器，防護涵蓋範圍就已經超越大多數人了。

## 我應該付費使用 NextDNS 嗎？
考量到豐富的功能，[NextDNS](https://nextdns.io/?from=xujj63g5) 的價格相當實惠，每年僅需 19.90 美元即可在無限台裝置上使用。只要它能替家人擋下一次惡意攻擊事件，這筆費用就完全值回票價。

## 啟用越多功能會影響 NextDNS 的速度嗎？<sup>[1](https://github.com/yokoffing/NextDNS-Config/issues/12#issue-1465457977) [2](https://www.reddit.com/r/nextdns/comments/135utai/comment/jilbus8/?=&context=3)</sup>

您開啟的設定數量不會影響 DNS 的解析延遲。

## 如果我已經在系統層級使用 NextDNS，還需要在瀏覽器層級設定 DoH 嗎？
除非您想為瀏覽器單獨套用不同的設定檔，否則這並[非必要](https://www.reddit.com/r/nextdns/comments/yfjvqy/is_it_redundant_to_set_at_doh_at_browserlevel_if/iu3vjzt/?context=3)。不過，我仍建議您[在網頁瀏覽器中完成設定](https://itechtics.com/dns-over-https/#how-to-enable-or-disable-dns-over-https-in-your-browsers)。

## 我同時有路由器設定檔和裝置設定檔，裝置會優先採用哪一個？
裝置會優先使用由 [NextDNS](https://nextdns.io/?from=xujj63g5) 應用程式或已安裝的[根憑證授權單位（Root CA）](https://help.nextdns.io/t/g9hmv0a/how-to-install-and-trust-nextdns-root-ca)所指定的設定檔。若裝置未設定獨立的設定檔，則會改用 Wi-Fi／路由器的設定。<sup>[1](https://www.reddit.com/r/nextdns/comments/yf4hnv/question_about_home_router_and_app_running_in/)</sup>

## 安全性、隱私權與匿名性有什麼區別？
請參閱[文章說明](https://thenewoil.org/en/guides/prologue/secprivanon/) | [影片解說](https://www.youtube.com/watch?v=Wpkh-hfULgE)

## NextDNS 會對我的網際網路服務供應商（ISP）隱藏連線活動嗎？
加密的 DNS 查詢可提升隱私權與安全性，讓您的 ISP 無法窺探您搜尋及造訪了哪些網站。

然而，加密 DNS 無法向 ISP 隱藏目標網站的 IP 位址。雖然 ISP 看不到您想存取的具體網域，但仍能察覺您連線至 Cloudflare 或 AWS 等 DNS 伺服器。如果您反覆向某個 IP 位址傳送資料，ISP 仍能推測您正在造訪該位址對應的網站。

## 我需要 VPN 嗎？
IVPN [指出](https://www.ivpn.net/blog/why-you-dont-need-a-vpn/)，您通常只在以下三種情況才需要 VPN：

1. 對網站與點對點（P2P）網路隱藏真實 IP 位址，防止 ISP 與行動電信業者追蹤您的線上活動。

2. 在機場、飯店、咖啡廳與圖書館等公共 Wi-Fi 環境中，防範[中間人攻擊](https://en.wikipedia.org/wiki/Man-in-the-middle_attack)及其他[常見無線網路攻擊](https://en.wikipedia.org/wiki/Evil_twin_(wireless_networks))。

3. 繞過網路審查或地理限制，存取遭封鎖的網站與內容。

歸根結底，除非您的[威脅模型](https://thenewoil.org/en/guides/prologue/threat-model/)確實有此需求，否則並不需要 VPN。若有需要，可參考 [Techlore](https://www.techlore.tech/vpn.html) 與 [Tom Spark Reviews](https://www.vpntierlist.com/vpn-tier-list-2024) 的 VPN 推薦清單。

***
# 相關提及與參考 :books:

### 使用者評論
* 請參閱[此處](https://socialgrep.com/search?query=yokoffing%2Cnextdns)

### YouTube
* [The ULTIMATE Guide to Mastering NextDNS!](https://www.youtube.com/watch?v=WUG57ynLb8I&t=2230s) | [補充說明](https://github.com/techlore/channel-content/issues/43)（2023 年 7 月）

### 文章
* [Knot Resolver — with ad blocking](https://blog.cavelab.dev/2022/12/knot-resolver-ad-blocking/)（2022 年 12 月）
* [Privacy Toolkit: NextDNS](https://stephenbolen.com/privacy-toolkit-nextdns/#:~:text=I%20found%20a%20wonderful%20guide%20on%20GitHub%20that%20walks%20through%20the%20optimal%20NextDNS%20configuration)（2022 年 9 月）

### 指南
* [A comprehensive guide to setting up NextDNS](https://itsjake.me/blog/a-comprehensive-guide-to-setting-up-nextdns/)（2023 年 9 月）
* [FMHY: DNS Adblocking](https://github.com/nbats/FMHYedit/blob/main/AdblockVPNGuide.md#-dns-adblocking) → NextDNS → Guide
* [hagezi/dns-blocklists](https://github.com/hagezi/dns-blocklists#department_store-nextdns---limited-freepaid-) → Online DNS Services

### 貢獻
* [Hagezi](https://github.com/hagezi/dns-blocklists/issues?q=author%3Ayokoffing) | [提及](https://github.com/hagezi/dns-blocklists/issues?q=mentions%3Ayokoffing)
* [1Hosts](https://github.com/badmojr/1Hosts/issues?q=author%3Ayokoffing)
* [Easylist](https://github.com/easylist/easylist/issues?q=author%3Ayokoffing)
* [uBlock Origin](https://github.com/uBlockOrigin/uAssets/issues?q=author%3Ayokoffing)
* [AdGuard](https://github.com/AdguardTeam/AdguardFilters/issues?q=author%3Ayokoffing)
