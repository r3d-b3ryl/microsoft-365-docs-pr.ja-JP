---
title: Microsoft Defender for Endpoint Office 365 と共に Microsoft Defender を使用する
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
description: Microsoft Defender for Office 365 を Microsoft Defender for Endpoint と共に使用して、デバイスやメール コンテンツに対する脅威に関する詳細情報を取得します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939334"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="02e34-104">Microsoft Defender for Endpoint Office 365 と共に Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="02e34-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="02e34-105">[Microsoft Defender for Office 365](office-365-atp.md) は、Microsoft Defender for Endpoint と一緒 [に動作するように構成できます](https://docs.microsoft.com/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="02e34-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="02e34-106">Office 365 用 Microsoft Defender と Microsoft Defender for Endpoint を統合すると、セキュリティ運用チームは、ユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02e34-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="02e34-107">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、それらのデバイスに対して生成された最新のアラートの数をエンドポイント用 Microsoft Defender で確認できます。</span><span class="sxs-lookup"><span data-stu-id="02e34-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="02e34-108">次の図は、[デバイス]タブで Microsoft Defender for Endpoint 統合が有効になっていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="02e34-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>

![Microsoft Defender for Endpoint が有効になっていると、アラートが表示されたデバイスの一覧が表示されます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="02e34-110">この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つがアラートを持っているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="02e34-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="02e34-111">デバイスのリンクをクリックすると、Microsoft Defender セキュリティ センター () でページが開きます <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="02e34-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="02e34-112">**[Microsoft Defender セキュリティ センター (Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** for Endpoint ポータルとも呼ばれます) の詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="02e34-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="02e34-113">要件</span><span class="sxs-lookup"><span data-stu-id="02e34-113">Requirements</span></span>

- <span data-ttu-id="02e34-114">組織には、Microsoft Defender for Office 365 (または Office 365 E5) と Microsoft Defender for Endpoint が必要です。</span><span class="sxs-lookup"><span data-stu-id="02e34-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="02e34-115">セキュリティ センター コンプライアンス センターで割り当てられているセキュリティ管理者の役割 (セキュリティ管理者など) がグローバル管理者 [&必要があります](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="02e34-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="02e34-116">(「[セキュリティ/コンプライアンス センターのアクセス&」を参照)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="02e34-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="02e34-117">セキュリティ センター コンプライアンス センターと Microsoft Defender セキュリティ センターで、エクスプローラー (またはリアルタイムの検出 [)](threat-explorer.md) &両方にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e34-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="02e34-118">Microsoft Defender for Office 365 を Microsoft Defender for Endpoint と統合するには</span><span class="sxs-lookup"><span data-stu-id="02e34-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="02e34-119">Office 365 用 Microsoft Defender と Microsoft Defender for Endpoint の統合は、セキュリティ & コンプライアンス センターと Microsoft Defender セキュリティ センターの両方を使用してセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="02e34-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="02e34-120">グローバル管理者またはセキュリティ管理者として、移動して <https://protection.office.com> サインインします。</span><span class="sxs-lookup"><span data-stu-id="02e34-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="02e34-121">(これにより、コンプライアンス センターの Office 365 セキュリティ&表示されます)。</span><span class="sxs-lookup"><span data-stu-id="02e34-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="02e34-122">ナビゲーション ウィンドウで、[脅威管理 **エクスプローラー] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="02e34-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![脅威の管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="02e34-124">画面の右上隅で **、[Defender for Endpoint Settings (MDE Settings] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="02e34-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="02e34-125">[Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[Microsoft Defender for Endpoint への接続 **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="02e34-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint 接続](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="02e34-127">Microsoft Defender セキュリティ センター () に移動します <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="02e34-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="02e34-128">ナビゲーション バーで、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="02e34-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="02e34-129">次に、[全般] **で**[高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="02e34-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="02e34-130">**365** 脅威インテリジェンスOfficeまで下にスクロールし、接続を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="02e34-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="02e34-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="02e34-132">Related articles</span></span>

[<span data-ttu-id="02e34-133">Office 365 の脅威の調査および対応機能</span><span class="sxs-lookup"><span data-stu-id="02e34-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="02e34-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="02e34-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="02e34-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02e34-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
