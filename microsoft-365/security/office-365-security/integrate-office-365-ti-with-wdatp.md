---
title: Office 365 の ATP と Microsoft Defender ATP を統合する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: 1574def6959bf63f061ff35bae71aed9657de436
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036367"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ef10e-103">Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する</span><span class="sxs-lookup"><span data-stu-id="ef10e-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="ef10e-104">組織のセキュリティチームに参加している場合は、 [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して[Office 365 advanced threat protection](office-365-atp.md)と関連調査および応答機能を統合することができます。</span><span class="sxs-lookup"><span data-stu-id="ef10e-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="ef10e-105">これは、Office 365 で脅威を調査しているときに、ユーザーのコンピューターが危険にさらされているかどうかをすばやく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef10e-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="ef10e-106">たとえば、統合が有効になると、検出された電子メールメッセージの受信者によって使用されるコンピューターの一覧、およびそれらのコンピューターが Microsoft Defender Advanced Threat Protection で保持している最近の通知の数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef10e-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="ef10e-107">次の図は、Microsoft Defender ATP 統合が有効になっている場合に表示される [**デバイス**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef10e-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Microsoft Defender ATP が有効になっている場合は、アラートがあるデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ef10e-109">この例では、電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ef10e-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="ef10e-110">デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンターにそのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef10e-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ef10e-111">要件</span><span class="sxs-lookup"><span data-stu-id="ef10e-111">Requirements</span></span>

- <span data-ttu-id="ef10e-112">組織では、Office 365 ATP Plan 2 (または Office 365 E5) と Microsoft Defender ATP を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef10e-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="ef10e-113">[ &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)では、全体管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef10e-113">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ef10e-114">([セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照)</span><span class="sxs-lookup"><span data-stu-id="ef10e-114">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ef10e-115">セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の[エクスプローラー (またはリアルタイム検出)](threat-explorer.md)にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef10e-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="ef10e-116">Microsoft Defender ATP を使用して Office 365 ATP を統合するには</span><span class="sxs-lookup"><span data-stu-id="ef10e-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="ef10e-117">Microsoft Defender ATP との Office 365 ATP の統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用してセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="ef10e-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="ef10e-118">グローバル管理者またはセキュリティ管理者として[https://protection.office.com](https://protection.office.com) 、に移動して、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef10e-118">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ef10e-119">[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef10e-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="ef10e-120">![脅威管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ef10e-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ef10e-121">画面の右上にある [ **Wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef10e-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="ef10e-122">[Microsoft Defender ATP 接続] ダイアログボックスで、[ **WINDOWS ATP への接続**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ef10e-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="ef10e-123">![Microsoft Defender ATP 接続](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ef10e-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="ef10e-124">Microsoft Defender セキュリティセンター ([https://securitycenter.windows.com](https://securitycenter.windows.com)) で接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ef10e-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef10e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef10e-125">Related topics</span></span>

[<span data-ttu-id="ef10e-126">Office 365 の脅威の調査および応答機能</span><span class="sxs-lookup"><span data-stu-id="ef10e-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ef10e-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ef10e-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

