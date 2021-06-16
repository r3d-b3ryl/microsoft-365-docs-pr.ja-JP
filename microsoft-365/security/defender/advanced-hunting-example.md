---
title: Microsoft Defender for microsoft Defender for Office 365
description: 高度な検索を使用して電子メールの脅威の検索を開始する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965150"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="7243c-104">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7243c-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7243c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7243c-105">**Applies to:**</span></span>
- <span data-ttu-id="7243c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7243c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7243c-107">高度な検出を使用してメールの脅威の検索を開始しますか?</span><span class="sxs-lookup"><span data-stu-id="7243c-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="7243c-108">実行する操作:</span><span class="sxs-lookup"><span data-stu-id="7243c-108">Try this:</span></span>

<span data-ttu-id="7243c-109">[Microsoft Defender for Office 365の記事](/microsoft-365/security/office-365-security/defender-for-office-365)の「[使用を開始する](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)」セクションには、次のような論理的な早期構成用の単位があります。</span><span class="sxs-lookup"><span data-stu-id="7243c-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="7243c-110">名前に 'Anti' を含むすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="7243c-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="7243c-111">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="7243c-111">Anti-malware</span></span>
   - <span data-ttu-id="7243c-112">フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="7243c-112">Anti-phishing</span></span>
   - <span data-ttu-id="7243c-113">スパム対策</span><span class="sxs-lookup"><span data-stu-id="7243c-113">Anti-spam</span></span>
2. <span data-ttu-id="7243c-114">名前に 'セーフ' を含むすべてを設定します。</span><span class="sxs-lookup"><span data-stu-id="7243c-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="7243c-115">安全なリンク</span><span class="sxs-lookup"><span data-stu-id="7243c-115">Safe Links</span></span>
   - <span data-ttu-id="7243c-116">安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="7243c-116">Safe Attachments</span></span>
3. <span data-ttu-id="7243c-117">ワークロードを保護する (例:</span><span class="sxs-lookup"><span data-stu-id="7243c-117">Defend the workloads (ex.</span></span> <span data-ttu-id="7243c-118">SharePointオンライン、OneDrive、およびTeams)。</span><span class="sxs-lookup"><span data-stu-id="7243c-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="7243c-119">0 時間自動削除で保護します。</span><span class="sxs-lookup"><span data-stu-id="7243c-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="7243c-120">[リンク](../office-365-security/protect-against-threats.md)をクリックすると、一気にジャンプして、第 1 日目から使用できる構成を入手できます。</span><span class="sxs-lookup"><span data-stu-id="7243c-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="7243c-121">**開始** の最後の手順は、**ゼロアワー自動消去**(ZAP) によるユーザー保護です。</span><span class="sxs-lookup"><span data-stu-id="7243c-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="7243c-122">ZAP で不審なメールや悪意のあるメール、配信後のメールの自動消去が成功したどうかを知るのはとても重要です。</span><span class="sxs-lookup"><span data-stu-id="7243c-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="7243c-123">問題を探し出す場合に、Kusto クエリ言語にすばやく移動できることは、2 つのセキュリティ センターを集約する利点です。</span><span class="sxs-lookup"><span data-stu-id="7243c-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="7243c-124">セキュリティ チームは、次の手順を実行して、ZAP ミスを監視 [](https://security.microsoft.com/advanced-hunting) \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="7243c-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="7243c-125">[高度な検索] ページで、[クエリ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7243c-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="7243c-126">次のクエリを[クエリ] ウィンドウにコピーします。</span><span class="sxs-lookup"><span data-stu-id="7243c-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="7243c-127">**[クエリの実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7243c-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="クエリ パネルの上部で [クエリ] を選択し、過去 7 日間の ZAP アクションをキャプチャするために Kusto クエリを実行した [高度な検索] ページ ([ハンティング] の下)。":::

<span data-ttu-id="7243c-129">このクエリのデータは、クエリ自体の下の結果パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7243c-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="7243c-130">結果には、カスタマイズ可能な結果セットに 'DeviceName', 'AccountDisplayName'、および 'ZapTime' が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7243c-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="7243c-131">ユーザーの記録用に、結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7243c-131">Results can also be exported for your records.</span></span> <span data-ttu-id="7243c-132">クエリがもう一度必要な場合は、**[保存する]** > **[以下の名前で保存する]** の順に選択し、クエリ、共有クエリ、またはコミュニティ クエリの一覧にそのクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="7243c-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="7243c-133">関連情報</span><span class="sxs-lookup"><span data-stu-id="7243c-133">Related information</span></span>
- [<span data-ttu-id="7243c-134">高度な狩猟のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="7243c-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7243c-135">概要 - 高度な検索</span><span class="sxs-lookup"><span data-stu-id="7243c-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
