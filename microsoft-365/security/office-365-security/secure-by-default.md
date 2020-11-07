---
title: Office 365 で既定でセキュリティ保護されている
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 組織の電子メールセキュリティレポートを検索して使用する方法について説明します。 電子メールセキュリティレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944479"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="dad72-104">Office 365 で既定でセキュリティ保護されている</span><span class="sxs-lookup"><span data-stu-id="dad72-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dad72-105">[既定でセキュリティ保護] は、可能な限り最も安全な既定の設定を定義するために使用される用語です。</span><span class="sxs-lookup"><span data-stu-id="dad72-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="dad72-106">ただし、セキュリティは生産性にバランスをとる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad72-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="dad72-107">これには、次のようなバランスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dad72-107">This can include balancing across:</span></span>
- <span data-ttu-id="dad72-108">有用性: 設定は、ユーザーの生産性を向上させることはできません。</span><span class="sxs-lookup"><span data-stu-id="dad72-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="dad72-109">リスク: セキュリティが重要なアクティビティをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dad72-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="dad72-110">従来の設定: 新しい高度な設定が改善された場合でも、以前の製品や機能のいくつかの構成は、ビジネス上の理由から維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad72-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="dad72-111">Exchange Online のメールボックスを使用する Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="dad72-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="dad72-112">この保護には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dad72-112">This  protection includes:</span></span>
1. <span data-ttu-id="dad72-113">疑いのあるマルウェアを含む電子メールは自動的に検疫され、受信者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="dad72-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="dad72-114">[EOP でマルウェア対策ポリシーを構成するを](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad72-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="dad72-115">「高信頼」として識別されたフィッシングメールは、スパム対策ポリシーアクションに従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="dad72-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="dad72-116">[EOP の「スパム対策ポリシーの構成」を](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide)参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad72-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="dad72-117">Microsoft は、お客様に既定でセキュリティを維持することを目的としているため、一部のテナントは、マルウェアや高信頼フィッシングには適用されません。</span><span class="sxs-lookup"><span data-stu-id="dad72-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="dad72-118">これらのオーバーライドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dad72-118">These overrides include:</span></span>
- <span data-ttu-id="dad72-119">許可された送信者リストまたは許可されたドメインリスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="dad72-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="dad72-120">Outlook の差出人セーフリスト</span><span class="sxs-lookup"><span data-stu-id="dad72-120">Outlook Safe senders</span></span>
- <span data-ttu-id="dad72-121">IP 許可一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="dad72-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="dad72-122">これらのオーバーライドの詳細については、「 [安全な送信者リストを作成](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad72-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="dad72-123">セキュリティで保護されている既定の設定は、有効または無効にすることはできませんが、潜在的な危険または不要なメッセージをメールボックスから保持するためのボックスからフィルターを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dad72-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="dad72-124">マルウェアと信頼度の高いフィッシングを検疫に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad72-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="dad72-125">マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="dad72-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="dad72-126">詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad72-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="dad72-127">例外</span><span class="sxs-lookup"><span data-stu-id="dad72-127">Exceptions</span></span>
<span data-ttu-id="dad72-128">すべてのフィルターをバイパスする唯一のオーバーライドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dad72-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="dad72-129">Exchange トランスポートルール (ETR)/メールフロールール。</span><span class="sxs-lookup"><span data-stu-id="dad72-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="dad72-130">メールフロールールを使用して、EOP のメッセージでスパム信頼レベル (SCL) を設定します。</span><span class="sxs-lookup"><span data-stu-id="dad72-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="dad72-131">テナントの許可/ブロックリスト: テナントの許可/ブロックリスト内の Url とファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="dad72-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="dad72-132">これらの種類のオーバーライドは、次のような場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dad72-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="dad72-133">フィッシングのシミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱性のあるユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dad72-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="dad72-134">セキュリティ/SecOps メールボックス: セキュリティチームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好および不良)。</span><span class="sxs-lookup"><span data-stu-id="dad72-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="dad72-135">チームは、悪意のあるコンテンツが含まれているかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="dad72-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="dad72-136">サードパーティのフィルター: サードパーティ製のフィルターがメールフィルターを管理するために、サードパーティベンダーの中には EOP (SCL =-1) をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dad72-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="dad72-137">Microsoft では、EOP をオフにすることは推奨されていません。 EOP は、Defender for Office 365 のために必要です。</span><span class="sxs-lookup"><span data-stu-id="dad72-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="dad72-138">誤検知: Microsoft によってまだ分析されている特定のメッセージを [管理者の送信から](admin-submission.md)許可することができます。</span><span class="sxs-lookup"><span data-stu-id="dad72-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="dad72-139">すべてのオーバーライドと同様に、一時的なものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dad72-139">As with all overrides, it is recommended that they are temporary.</span></span>
