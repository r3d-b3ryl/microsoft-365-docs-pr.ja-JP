---
title: エンドポイントの Microsoft Defender と Office 365 の Microsoft Defender を併用する
f1.keywords:
- NOCSH
keywords: 統合、Microsoft Defender、ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: エンドポイントとして microsoft defender for Office 365 を使用して、デバイスや電子メールコンテンツに対する脅威に関する詳細な情報を取得します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b8bec8d3ebe52de9b4e1b919b2aceee20b5b5b0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842358"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="ecb21-104">エンドポイントの Microsoft Defender と Office 365 の Microsoft Defender を併用する</span><span class="sxs-lookup"><span data-stu-id="ecb21-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ecb21-105">Microsoft defender [For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)は、[エンドポイントの microsoft defender](https://docs.microsoft.com/windows/security/threat-protection)と連携するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="ecb21-105">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="ecb21-106">Microsoft defender for Office 365 とエンドポイントの Microsoft Defender を統合することで、ユーザーのデバイスが危険にさらされている場合に、セキュリティ運用チームが迅速に監視し、アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ecb21-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="ecb21-107">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メールメッセージによって影響を受ける可能性があるデバイスを確認したり、エンドポイント用 Microsoft Defender のデバイスに対して生成された最近の通知の数を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="ecb21-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="ecb21-108">次の図は、エンドポイントの統合を有効にした状態で、[ **デバイス** ] タブがどのようなものかを示しています。</span><span class="sxs-lookup"><span data-stu-id="ecb21-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![エンドポイントの Microsoft Defender が有効になっている場合は、アラートがあるデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ecb21-110">この例では、検出された電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ecb21-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="ecb21-111">デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンター () にそのページが表示さ [https://securitycenter.windows.com](https://securitycenter.windows.com) れます。</span><span class="sxs-lookup"><span data-stu-id="ecb21-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="ecb21-112">**[Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (エンドポイントポータルの microsoft defender とも呼ばれます) の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecb21-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ecb21-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="ecb21-113">Requirements</span></span>

- <span data-ttu-id="ecb21-114">組織には、Microsoft Defender for Office 365 (または Office 365 E5) および Microsoft Defender for Endpoint が必要です。</span><span class="sxs-lookup"><span data-stu-id="ecb21-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="ecb21-115">[セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)では、全体管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb21-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ecb21-116">( [セキュリティ &amp; コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照)</span><span class="sxs-lookup"><span data-stu-id="ecb21-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ecb21-117">セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の [エクスプローラー (またはリアルタイム検出)](threat-explorer.md) にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb21-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="ecb21-118">Microsoft defender for Office 365 とエンドポイントの microsoft defender を統合するには</span><span class="sxs-lookup"><span data-stu-id="ecb21-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="ecb21-119">Microsoft defender for Office 365 とエンドポイントの Microsoft Defender との統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="ecb21-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="ecb21-120">グローバル管理者またはセキュリティ管理者として、に移動して、に [https://protection.office.com](https://protection.office.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="ecb21-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="ecb21-121">(これにより、Office 365 セキュリティ & コンプライアンスセンターに移動します。)</span><span class="sxs-lookup"><span data-stu-id="ecb21-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="ecb21-122">ナビゲーションウィンドウで、[ **脅威管理** エクスプローラー] を選択し  >  **Explorer** ます。</span><span class="sxs-lookup"><span data-stu-id="ecb21-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="ecb21-123">![脅威管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ecb21-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ecb21-124">画面の右上隅で、[ **エンドポイント設定] に [Defender** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb21-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="ecb21-125">[エンドポイントの接続の Microsoft defender] ダイアログボックスで、[ **エンドポイントの Microsoft defender への接続** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ecb21-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="ecb21-126">![エンドポイント接続のための Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ecb21-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="ecb21-127">Microsoft Defender セキュリティセンター () に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) します。</span><span class="sxs-lookup"><span data-stu-id="ecb21-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="ecb21-128">ナビゲーションバーで、[ **設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb21-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="ecb21-129">[ **全般** ] で、[ **高度な機能** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb21-129">Then, under **General** , choose **Advanced features**.</span></span>

7. <span data-ttu-id="ecb21-130">[ **Office 365 の脅威インテリジェンス接続** ] まで下にスクロールし、接続をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ecb21-130">Scroll down to **Office 365 Threat Intelligence connection** , and turn the connection on.</span></span><br/><span data-ttu-id="ecb21-131">![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="ecb21-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="ecb21-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="ecb21-132">Related articles</span></span>

[<span data-ttu-id="ecb21-133">Office 365 の脅威の調査および応答機能</span><span class="sxs-lookup"><span data-stu-id="ecb21-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ecb21-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ecb21-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="ecb21-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ecb21-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
