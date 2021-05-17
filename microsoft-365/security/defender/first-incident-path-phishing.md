---
title: フィッシングメール攻撃の例
description: フィッシング攻撃の分析例を説明します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299990"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="f150e-104">フィッシングメール攻撃の例</span><span class="sxs-lookup"><span data-stu-id="f150e-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f150e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f150e-105">**Applies to:**</span></span>
- <span data-ttu-id="f150e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f150e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f150e-107">Microsoft 365 Defender は、電子メールを介して配信される悪意のある添付ファイルを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f150e-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="f150e-108">Office [365](https://protection.office.com/) セキュリティ/コンプライアンス センターは Microsoft 365 Defender と統合されています。セキュリティ アナリストは、Office 365 からの脅威 (電子メールの添付ファイルなど) を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="f150e-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="f150e-109">たとえば、アナリストに複数ステージのインシデントが割り当てられたとします。</span><span class="sxs-lookup"><span data-stu-id="f150e-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="複数ステージインシデントの例"::: 

<span data-ttu-id="f150e-111">インシデントの **[アラート** ] タブに、Defender から 365 Office Microsoft Cloud App Security のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f150e-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="f150e-112">アナリストは、電子メール メッセージの通知を選択Office 365 アラートの Defender にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="f150e-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="f150e-113">アラートの詳細がサイド ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f150e-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="電子メールアラートの例":::
 
<span data-ttu-id="f150e-115">さらに下にスクロールすると、より多くの情報が表示され、影響を受ける悪意のあるファイルとユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f150e-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="電子メール アラートのユーザーとファイルへの影響の例":::
  
<span data-ttu-id="f150e-117">[アラート **を開く] ページ** を選択すると、特定のアラートに移動し、リンクを選択することでさまざまな情報を詳細に表示できます。</span><span class="sxs-lookup"><span data-stu-id="f150e-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="f150e-118">実際の電子メール メッセージは、パネルの下部に向かって **[エクスプローラー** でメッセージを表示する] を選択して表示できます。</span><span class="sxs-lookup"><span data-stu-id="f150e-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="アラートの詳細の例"::: 

<span data-ttu-id="f150e-120">これにより、アナリストが [脅威の管理] ページに移動し、電子メールの件名、受信者、送信者、その他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f150e-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="f150e-121">**[特別な** アクション **] の下の** ZAP は、ゼロ時間自動削除機能が実装されたとアナリストに指示します。</span><span class="sxs-lookup"><span data-stu-id="f150e-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="f150e-122">ZAP は、組織全体のメールボックスから悪意のあるメッセージやスパム メッセージを自動的に検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="f150e-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="f150e-123">詳細については [、「Exchange Online のゼロ時間自動削除 (ZAP)」を参照してください](../office-365-security/zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="f150e-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="f150e-124">[アクション] を選択すると、特定のメッセージに対して他のアクションを **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="f150e-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="電子メール メッセージに対して実行できるその他のアクションの例"::: 

## <a name="next-step"></a><span data-ttu-id="f150e-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="f150e-126">Next step</span></span>

<span data-ttu-id="f150e-127">ID ベース [の攻撃調査パスを](first-incident-path-identity.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="f150e-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="f150e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f150e-128">See also</span></span>

- [<span data-ttu-id="f150e-129">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="f150e-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f150e-130">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="f150e-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f150e-131">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="f150e-131">Manage incidents</span></span>](manage-incidents.md)
