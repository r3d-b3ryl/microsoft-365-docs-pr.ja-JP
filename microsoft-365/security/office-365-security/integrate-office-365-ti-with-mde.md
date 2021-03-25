---
title: Microsoft Defender for Endpoint と共Office 365 の Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender for Office 365 と Microsoft Defender for Endpoint を組み合わせて使用して、デバイスや電子メール コンテンツに対する脅威に関する詳細情報を取得します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c2e7a3eeb9576b53723a786de85f0c4bece679b4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205483"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d5119-104">Microsoft Defender for Endpoint と共Office 365 の Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="d5119-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d5119-105">[Microsoft Defender for Office 365 は](defender-for-office-365.md) 、Microsoft Defender for Endpoint で動作 [するように構成できます](/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="d5119-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="d5119-106">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint を統合すると、ユーザーのデバイスが危険にさらされている場合、セキュリティ運用チームが迅速に監視し、アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5119-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="d5119-107">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5119-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d5119-108">次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。</span><span class="sxs-lookup"><span data-stu-id="d5119-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Microsoft Defender for Endpoint が有効になっている場合は、通知を含むデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="d5119-110">この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5119-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="d5119-111">デバイスのリンクをクリックすると、Microsoft Defender セキュリティ センター () でページが開きます <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="d5119-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="d5119-112">**[Microsoft Defender セキュリティ センターの詳細 (Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use)** for Endpoint ポータルとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="d5119-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="d5119-113">要件</span><span class="sxs-lookup"><span data-stu-id="d5119-113">Requirements</span></span>

- <span data-ttu-id="d5119-114">組織には、Microsoft Defender for Office 365 (または Office 365 E5) と Microsoft Defender for Endpoint が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5119-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="d5119-115">グローバル管理者またはセキュリティ管理者の役割 (セキュリティ管理者など) がセキュリティ コンプライアンス センターに割り当てられている& [必要があります](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="d5119-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d5119-116">(「 [セキュリティ コンプライアンス センターのアクセス許可&」を参照してください](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="d5119-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="d5119-117">セキュリティ コンプライアンス センターと Microsoft Defender セキュリティ センターの両方のエクスプローラー (またはリアルタイム検出 [)](threat-explorer.md) &アクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5119-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d5119-118">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint を統合するには</span><span class="sxs-lookup"><span data-stu-id="d5119-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d5119-119">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint の統合は、セキュリティ & コンプライアンス センターと Microsoft Defender セキュリティ センターの両方を使用してセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="d5119-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="d5119-120">グローバル管理者またはセキュリティ管理者として、アクセスして <https://protection.office.com> サインインします。</span><span class="sxs-lookup"><span data-stu-id="d5119-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="d5119-121">(これにより、コンプライアンス センター Office 365 &にアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="d5119-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="d5119-122">ナビゲーション ウィンドウで、[脅威管理エクスプローラー] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5119-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![[脅威の管理] メニューの [エクスプローラー]](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="d5119-124">画面の右上隅で、[Defender **for Endpoint Settings (MDE Settings) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5119-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="d5119-125">[Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[エンドポイント用 **Microsoft Defender に接続する] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="d5119-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![エンドポイント接続用 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="d5119-127">Microsoft Defender セキュリティ センター ( ) に移動します <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="d5119-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="d5119-128">ナビゲーション バーで、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5119-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="d5119-129">次に、[全般] **で 、[** 高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5119-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="d5119-130">**365 脅威インテリジェンスOfficeまで** 下にスクロールし、接続を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="d5119-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="d5119-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="d5119-132">Related articles</span></span>

[<span data-ttu-id="d5119-133">365 の脅威の調査と対応Office</span><span class="sxs-lookup"><span data-stu-id="d5119-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="d5119-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="d5119-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="d5119-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5119-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)