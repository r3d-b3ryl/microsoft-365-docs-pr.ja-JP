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
description: Exchange Online Protection (EOP) の [既定でセキュリティ保護] の設定についての詳細情報
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945332"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="41134-103">Office 365 で既定でセキュリティ保護されている</span><span class="sxs-lookup"><span data-stu-id="41134-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41134-104">[既定でセキュリティ保護] は、可能な限り最も安全な既定の設定を定義するために使用される用語です。</span><span class="sxs-lookup"><span data-stu-id="41134-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="41134-105">ただし、セキュリティは生産性にバランスをとる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41134-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="41134-106">これには、次のようなバランスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="41134-106">This can include balancing across:</span></span>

- <span data-ttu-id="41134-107">有用性: 設定は、ユーザーの生産性を向上させることはできません。</span><span class="sxs-lookup"><span data-stu-id="41134-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="41134-108">リスク: セキュリティが重要なアクティビティをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41134-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="41134-109">従来の設定: 新しい高度な設定が改善された場合でも、以前の製品や機能のいくつかの構成は、ビジネス上の理由から維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41134-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="41134-110">Exchange Online のメールボックスを使用する Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="41134-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="41134-111">この保護には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41134-111">This protection includes:</span></span>

1. <span data-ttu-id="41134-112">疑いのあるマルウェアを含む電子メールは自動的に検疫され、受信者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="41134-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="41134-113">[EOP でマルウェア対策ポリシーを構成するを](configure-anti-malware-policies.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="41134-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="41134-114">「高信頼」として識別されたフィッシングメールは、スパム対策ポリシーアクションに従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="41134-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="41134-115">[EOP の「スパム対策ポリシーの構成」を](configure-your-spam-filter-policies.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="41134-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="41134-116">Microsoft は、お客様に既定でセキュリティを維持することを目的としているため、一部のテナントは、マルウェアや高信頼フィッシングには適用されません。</span><span class="sxs-lookup"><span data-stu-id="41134-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="41134-117">これらのオーバーライドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41134-117">These overrides include:</span></span>

- <span data-ttu-id="41134-118">許可された送信者リストまたは許可されたドメインリスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="41134-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="41134-119">Outlook の差出人セーフリスト</span><span class="sxs-lookup"><span data-stu-id="41134-119">Outlook Safe senders</span></span>
- <span data-ttu-id="41134-120">IP 許可一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="41134-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="41134-121">これらのオーバーライドの詳細については、「 [安全な送信者リストを作成](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41134-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="41134-122">セキュリティで保護されている既定の設定は、有効または無効にすることはできませんが、潜在的な危険または不要なメッセージをメールボックスから保持するためのボックスからフィルターを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="41134-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="41134-123">マルウェアと信頼度の高いフィッシングを検疫に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41134-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="41134-124">マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="41134-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="41134-125">詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41134-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="41134-126">例外</span><span class="sxs-lookup"><span data-stu-id="41134-126">Exceptions</span></span>

<span data-ttu-id="41134-127">すべてのフィルターをバイパスする唯一のオーバーライドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41134-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="41134-128">Exchange トランスポートルール (ETR)/メールフロールール。</span><span class="sxs-lookup"><span data-stu-id="41134-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="41134-129">メールフロールールを使用して、EOP のメッセージでスパム信頼レベル (SCL) を設定します。</span><span class="sxs-lookup"><span data-stu-id="41134-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="41134-130">テナントの許可/ブロックリスト: テナントの許可/ブロックリスト内の Url とファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="41134-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="41134-131">これらの種類のオーバーライドは、次のような場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41134-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="41134-132">フィッシングのシミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱性のあるユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41134-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="41134-133">セキュリティ/SecOps メールボックス: セキュリティチームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好および不良)。</span><span class="sxs-lookup"><span data-stu-id="41134-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="41134-134">チームは、悪意のあるコンテンツが含まれているかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="41134-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="41134-135">サードパーティのフィルター: サードパーティ製のフィルターがメールフィルターを管理するために、サードパーティベンダーの中には EOP (SCL =-1) をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41134-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="41134-136">Microsoft では、EOP をオフにすることは推奨されていません。 EOP は、Defender for Office 365 のために必要です。</span><span class="sxs-lookup"><span data-stu-id="41134-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="41134-137">誤検知: Microsoft によってまだ分析されている特定のメッセージを [管理者の送信から](admin-submission.md)許可することができます。</span><span class="sxs-lookup"><span data-stu-id="41134-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="41134-138">すべてのオーバーライドと同様に、一時的なものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41134-138">As with all overrides, it is recommended that they are temporary.</span></span>
