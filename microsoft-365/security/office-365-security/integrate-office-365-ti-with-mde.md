---
title: Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, Microsoft Defender for Endpoint
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
description: Microsoft Defender for Office 365 Microsoft Defender for Endpoint を使用して、デバイスやメール コンテンツに対する脅威に関する詳細な情報を取得します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3f1d92d2433267b89398c7f7f582a8d1ee8cdba5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878606"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="7b1ad-104">Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="7b1ad-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7b1ad-105">[Microsoft Defender for Office 365](defender-for-office-365.md)は[、Microsoft Defender for Endpoint で動作するように構成できます](/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="7b1ad-106">Microsoft Defender for Office 365 Microsoft Defender for Endpoint と統合すると、セキュリティ運用チームがユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="7b1ad-107">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="7b1ad-108">次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Microsoft Defender for Endpoint が有効になっている場合は、通知を含むデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="7b1ad-110">この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="7b1ad-111">デバイスのリンクをクリックすると、デバイスのページが [Microsoft Defender セキュリティ センター ( ) で開きます <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="7b1ad-112">**[詳しくは、Microsoft Defender セキュリティ センター](/windows/security/threat-protection/microsoft-defender-atp/use)** (Microsoft Defender for Endpoint ポータルとも呼ばれます)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="7b1ad-113">要件</span><span class="sxs-lookup"><span data-stu-id="7b1ad-113">Requirements</span></span>

- <span data-ttu-id="7b1ad-114">組織には、Microsoft Defender for Office 365 (Office 365 E5) と Microsoft Defender for Endpoint が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="7b1ad-115">グローバル管理者またはセキュリティ管理者の役割 (セキュリティ管理者など) がセキュリティ コンプライアンス センターに割り当てられている& [必要があります](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="7b1ad-116">(「 [セキュリティ コンプライアンス センターのアクセス許可&」を参照してください](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="7b1ad-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="7b1ad-117">セキュリティ コンプライアンス センターとセキュリティ コンプライアンス センターの[エクスプローラー (](threat-explorer.md)またはリアルタイム検出) の両方にアクセス&必要Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="7b1ad-118">Microsoft Defender for Office 365エンドポイントと統合するには</span><span class="sxs-lookup"><span data-stu-id="7b1ad-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7b1ad-119">Microsoft Defender for Office 365 Microsoft Defender for Endpoint との統合は、セキュリティ コンプライアンス センターとセキュリティ コンプライアンス センターの両方&使用してMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="7b1ad-120">グローバル管理者またはセキュリティ管理者として、アクセスして <https://protection.office.com> サインインします。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="7b1ad-121">(これにより、コンプライアンス センター Office 365セキュリティ &にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="7b1ad-122">ナビゲーション ウィンドウで、[脅威管理エクスプローラー] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![[脅威の管理] メニューの [エクスプローラー]](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="7b1ad-124">画面の右上隅で、[Defender **for Endpoint 設定 (MDE 設定) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="7b1ad-125">[Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[エンドポイント用 Microsoft Defender Connect **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![エンドポイント接続用 Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="7b1ad-127">[ ] ( ) のMicrosoft Defender セキュリティ センター移動 <https://securitycenter.windows.com> します。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="7b1ad-128">ナビゲーション バーで、[次へ]**を設定。**</span><span class="sxs-lookup"><span data-stu-id="7b1ad-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="7b1ad-129">次に、[全般] **で 、[** 高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="7b1ad-130">[脅威インテリジェンス]**接続Office 365下にスクロールし**、接続をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="7b1ad-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="7b1ad-132">関連資料</span><span class="sxs-lookup"><span data-stu-id="7b1ad-132">Related articles</span></span>

[<span data-ttu-id="7b1ad-133">脅威の調査と対応機能 (Office 365</span><span class="sxs-lookup"><span data-stu-id="7b1ad-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="7b1ad-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7b1ad-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="7b1ad-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b1ad-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
