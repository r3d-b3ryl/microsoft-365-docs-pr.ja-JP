---
title: Office 365 の ATP と Microsoft Defender ATP を統合する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合し、より詳細な脅威管理情報を表示します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086710"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="6f7f4-103">Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する</span><span class="sxs-lookup"><span data-stu-id="6f7f4-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="6f7f4-104">[Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (OFFICE 365 atp) は、 [Microsoft Defender advanced threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (microsoft defender atp) で動作するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="6f7f4-105">Microsoft Defender ATP を使用して Office 365 ATP を統合することにより、ユーザーのデバイスが危険にさらされている場合に、セキュリティ運用チームが迅速に監視してアクションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="6f7f4-106">たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メールメッセージによって影響を受ける可能性があるデバイス、およびそれらのデバイスが Microsoft Defender ATP で保持している最近の通知の数を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="6f7f4-107">次の図は、Microsoft Defender ATP の統合が有効になっている**デバイス**タブの外観を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Microsoft Defender ATP が有効になっている場合は、アラートがあるデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="6f7f4-109">この例では、検出された電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="6f7f4-110">デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンター () にそのページが表示さ [https://securitycenter.windows.com](https://securitycenter.windows.com) れます。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="6f7f4-111">Microsoft Defender セキュリティセンター (Microsoft Defender ATP ポータルとも呼ばれます)**[の詳細については、こちら](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6f7f4-112">要件</span><span class="sxs-lookup"><span data-stu-id="6f7f4-112">Requirements</span></span>

- <span data-ttu-id="6f7f4-113">組織では、Office 365 ATP Plan 2 (または Office 365 E5) と Microsoft Defender ATP を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="6f7f4-114">[セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)では、全体管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="6f7f4-115">([セキュリティ &amp; コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照)</span><span class="sxs-lookup"><span data-stu-id="6f7f4-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="6f7f4-116">セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の[エクスプローラー (またはリアルタイム検出)](threat-explorer.md)にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="6f7f4-117">Microsoft Defender ATP を使用して Office 365 ATP を統合するには</span><span class="sxs-lookup"><span data-stu-id="6f7f4-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="6f7f4-118">Microsoft Defender ATP との Office 365 ATP の統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用してセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="6f7f4-119">グローバル管理者またはセキュリティ管理者として、に移動して、に [https://protection.office.com](https://protection.office.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="6f7f4-120">(これにより、Office 365 セキュリティ & コンプライアンスセンターに移動します。)</span><span class="sxs-lookup"><span data-stu-id="6f7f4-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="6f7f4-121">ナビゲーションウィンドウで、[**脅威管理**エクスプローラー] を選択し  >  **Explorer**ます。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="6f7f4-122">![脅威管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="6f7f4-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="6f7f4-123">画面の右上にある [ **Wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="6f7f4-124">[Microsoft Defender ATP 接続] ダイアログボックスで、[ **WINDOWS ATP への接続**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="6f7f4-125">![Microsoft Defender ATP 接続](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="6f7f4-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="6f7f4-126">Microsoft Defender セキュリティセンター () に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) します。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="6f7f4-127">ナビゲーションバーで、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="6f7f4-128">[**全般**] で、[**高度な機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="6f7f4-129">[ **Office 365 の脅威インテリジェンス接続**] まで下にスクロールし、接続をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6f7f4-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="6f7f4-130">![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="6f7f4-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="6f7f4-131">関連記事</span><span class="sxs-lookup"><span data-stu-id="6f7f4-131">Related articles</span></span>

[<span data-ttu-id="6f7f4-132">Office 365 の脅威の調査および応答機能</span><span class="sxs-lookup"><span data-stu-id="6f7f4-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="6f7f4-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6f7f4-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="6f7f4-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6f7f4-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
