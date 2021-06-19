---
title: Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028883"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="4a58a-104">Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="4a58a-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4a58a-105">[Microsoft Defender for Office 365](defender-for-office-365.md)は[、Microsoft Defender for Endpoint で動作するように構成できます](/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="4a58a-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="4a58a-106">Microsoft Defender for Office 365 Microsoft Defender for Endpoint と統合すると、セキュリティ運用チームがユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4a58a-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="4a58a-107">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a58a-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4a58a-108">次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。</span><span class="sxs-lookup"><span data-stu-id="4a58a-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Microsoft Defender for Endpoint が有効になっている場合は、通知を含むデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="4a58a-110">この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a58a-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="4a58a-111">デバイスのリンクをクリックすると、デバイスのページが Microsoft 365 Defender [(以前](../defender-endpoint/microsoft-defender-security-center.md)はMicrosoft Defender セキュリティ センター)。</span><span class="sxs-lookup"><span data-stu-id="4a58a-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="4a58a-112">新しいMicrosoft 365 Defenderポータルは、ユーザーを置き換Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="4a58a-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="4a58a-113">「Microsoft [Defender for Endpoint in Microsoft 365 Defender」を参照してください](../defender/microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="4a58a-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="4a58a-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="4a58a-114">Requirements</span></span>

- <span data-ttu-id="4a58a-115">組織には、Microsoft Defender for Office 365 (Office 365 E5) と Microsoft Defender for Endpoint が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a58a-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="4a58a-116">グローバル管理者か、セキュリティ管理者の役割 (セキュリティ管理者など) が管理者に割り当てられている必要Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4a58a-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="4a58a-117">(「[アクセス許可」を参照Microsoft 365 Defender)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="4a58a-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="4a58a-118">エクスプローラー (またはリアルタイム検出) にアクセス [できる必要があります](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="4a58a-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="4a58a-119">Microsoft Defender for Office 365エンドポイントと統合するには</span><span class="sxs-lookup"><span data-stu-id="4a58a-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4a58a-120">Microsoft Defender for Endpoint Office 365 Microsoft Defender の統合は、Defender for Endpoint と Defender for Endpoint の両方Office 365。</span><span class="sxs-lookup"><span data-stu-id="4a58a-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="4a58a-121">グローバル管理者またはセキュリティ管理者として、アクセスして [https://security.microsoft.com](https://security.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="4a58a-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="4a58a-122">(これにより、ポータルMicrosoft 365 Defenderされます)。</span><span class="sxs-lookup"><span data-stu-id="4a58a-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="4a58a-123">ナビゲーション ウィンドウで、[メール] を選択 **して&エクスプローラーを** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4a58a-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="4a58a-124">画面の右上隅にある [MDE ファイル] を **クリック設定。**</span><span class="sxs-lookup"><span data-stu-id="4a58a-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="4a58a-125">[Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[エンドポイント用 Microsoft Defender Connect **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="4a58a-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 接続":::

5. <span data-ttu-id="4a58a-127">ポータルに移動Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="4a58a-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="4a58a-128">ナビゲーション バーで、[次へ]**を設定。**</span><span class="sxs-lookup"><span data-stu-id="4a58a-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="4a58a-129">次に、[全般] **で 、[** 高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4a58a-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="4a58a-130">[脅威インテリジェンス]**接続Office 365下にスクロールし**、接続をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="4a58a-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="4a58a-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="4a58a-132">Related articles</span></span>

[<span data-ttu-id="4a58a-133">脅威の調査と対応機能 (Office 365</span><span class="sxs-lookup"><span data-stu-id="4a58a-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="4a58a-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4a58a-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="4a58a-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a58a-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
