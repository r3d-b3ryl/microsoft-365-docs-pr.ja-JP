---
title: 転送中データの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: '概要: 転送中に Microsoft がデータを暗号化する方法を簡単に説明します。'
ms.openlocfilehash: 0775d28a96f271a24406fd68c2ccb9fe4954e66d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637333"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="18c80-103">転送中のデータの暗号化</span><span class="sxs-lookup"><span data-stu-id="18c80-103">Encryption for data in transit</span></span>

<span data-ttu-id="18c80-104">お客様のデータを保存して保護することに加えて、Microsoft は暗号化テクノロジを使用して、転送中の顧客データを保護します。</span><span class="sxs-lookup"><span data-stu-id="18c80-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="18c80-105">データの送信中:</span><span class="sxs-lookup"><span data-stu-id="18c80-105">Data is in transit:</span></span>

- <span data-ttu-id="18c80-106">クライアントコンピューターが Microsoft サーバーと通信するとき。</span><span class="sxs-lookup"><span data-stu-id="18c80-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="18c80-107">Microsoft サーバーが他の Microsoft サーバーと通信する場合そして</span><span class="sxs-lookup"><span data-stu-id="18c80-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="18c80-108">Microsoft サーバーが Microsoft 以外のサーバーと通信する場合 (Exchange Online が電子メールを外部電子メールサーバーに配信する場合など)。</span><span class="sxs-lookup"><span data-stu-id="18c80-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="18c80-109">Microsoft サーバー間のデータセンター間の通信は TLS または IPsec 経由で行われ、お客様向けのすべてのサーバーは tls を使用してクライアントマシンとのセキュリティで保護されたセッションをネゴシエートします (たとえば、Exchange Online は TLS 1.2 を256ビットの暗号強度で使用します (FIPS 140-2 レベル 2-検証)。</span><span class="sxs-lookup"><span data-stu-id="18c80-109">Inter-datacenter communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="18c80-110">(Office 365 でサポートされている TLS 暗号スイートの一覧については、「 [office 365 の暗号化に関する技術リファレンスの詳細](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)」を参照してください)。これは、Outlook、Skype for Business、web 上の Outlook などのクライアントによって使用されるプロトコル (例: HTTP、POP3 など) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="18c80-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="18c80-111">公開証明書は、microsoft IT SSL によって発行された microsoft IT SSL で、送信された情報の機密性を保護するための内部 Microsoft ツールです。</span><span class="sxs-lookup"><span data-stu-id="18c80-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="18c80-112">Microsoft によって発行されるすべての証明書の長さは2048ビットです。また、Webtrust コンプライアンスでは、証明書が Microsoft によって所有されるパブリック IP アドレスにのみ発行されるようにするために、SSLAdmin が必要になります。</span><span class="sxs-lookup"><span data-stu-id="18c80-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="18c80-113">この条件を満たすことができない IP アドレスは、例外プロセスを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="18c80-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="18c80-114">使用されている TLS のバージョン、転送機密性 (FS) が有効になっているかどうか、暗号スイートの順番など、すべての実装の詳細を公開できます。</span><span class="sxs-lookup"><span data-stu-id="18c80-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="18c80-115">これらの詳細を確認する1つの方法は、 [QUALYS SSL Labs](https://www.ssllabs.com)などのサードパーティの web サイトを使用することです。</span><span class="sxs-lookup"><span data-stu-id="18c80-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="18c80-116">次のサービスの情報を表示する Qualys からの自動テストページへのリンクを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="18c80-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="18c80-117">Office 365 ポータル</span><span class="sxs-lookup"><span data-stu-id="18c80-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="18c80-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="18c80-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="18c80-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="18c80-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="18c80-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="18c80-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="18c80-121">Skype for Business (Web)</span><span class="sxs-lookup"><span data-stu-id="18c80-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="18c80-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="18c80-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="18c80-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18c80-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="18c80-124">Exchange Online Protection の場合、Url はテナント名によって異なります。ただし、すべてのお客様は**microsoft-com.mail.protection.outlook.com**を使用して Microsoft 365 をテストできます。</span><span class="sxs-lookup"><span data-stu-id="18c80-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
