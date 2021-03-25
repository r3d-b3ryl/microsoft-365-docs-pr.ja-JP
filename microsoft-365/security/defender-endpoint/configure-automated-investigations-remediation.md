---
title: 自動調査と修復機能の構成
description: Microsoft Defender for Endpoint で自動調査および修復機能をセットアップします。
keywords: 構成、セットアップ、自動化、調査、検出、アラート、修復、応答
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 31a1c79440a8c1edc2bc8e2f2a163ded2a92fd64
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165767"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="54f82-104">Microsoft Defender for Endpoint で自動調査および修復機能を構成する</span><span class="sxs-lookup"><span data-stu-id="54f82-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54f82-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="54f82-105">**Applies to:**</span></span>
- [<span data-ttu-id="54f82-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54f82-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54f82-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54f82-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="54f82-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="54f82-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54f82-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="54f82-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="54f82-110">組織が[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)Microsoft [Defender for Endpoint (Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/)を使用している場合、自動調査および修復機能により、セキュリティ運用チームの時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="54f82-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="54f82-111">このブログ記事で [説明するように、](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)これらの機能は、セキュリティ アナリストが脅威の調査と修復に必要な理想的な手順を模倣します。</span><span class="sxs-lookup"><span data-stu-id="54f82-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="54f82-112">[自動調査と修復の詳細については、次のリンクを参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="54f82-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="54f82-113">自動調査と修復を構成するには、</span><span class="sxs-lookup"><span data-stu-id="54f82-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="54f82-114">[機能を有効にする](#turn-on-automated-investigation-and-remediation)。そして</span><span class="sxs-lookup"><span data-stu-id="54f82-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="54f82-115">[デバイス グループを設定します](#set-up-device-groups)。</span><span class="sxs-lookup"><span data-stu-id="54f82-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="54f82-116">自動調査と修復を有効にする</span><span class="sxs-lookup"><span data-stu-id="54f82-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="54f82-117">グローバル管理者またはセキュリティ管理者として、Microsoft Defender セキュリティ センター ( ) に移動し [https://securitycenter.windows.com](https://securitycenter.windows.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="54f82-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="54f82-118">ナビゲーション ウィンドウで、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="54f82-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="54f82-119">[全般] **セクションで** 、[高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54f82-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="54f82-120">[自動調査]**と [アラートの\*\*\*\*自動解決] の両方をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="54f82-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="54f82-121">デバイス グループの設定</span><span class="sxs-lookup"><span data-stu-id="54f82-121">Set up device groups</span></span>

1. <span data-ttu-id="54f82-122">Microsoft Defender セキュリティ センター ( ) の [設定] ページの [アクセス許可] で、[デバイス [https://securitycenter.windows.com](https://securitycenter.windows.com) グループ]**を選択します**。  </span><span class="sxs-lookup"><span data-stu-id="54f82-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="54f82-123">[+ **デバイス グループの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54f82-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="54f82-124">次のように、少なくとも 1 つのデバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="54f82-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="54f82-125">デバイス グループの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="54f82-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="54f82-126">[オートメーション レベル **] ボックスの** 一覧で、[完全] などのレベルを選択し、脅威 **を自動的に修復します**。</span><span class="sxs-lookup"><span data-stu-id="54f82-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="54f82-127">オートメーション レベルは、修復アクションが自動的に実行されるのか、承認時にのみ実行されるのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="54f82-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="54f82-128">詳細については、「自動調査と [修復」の「オートメーション レベル」を参照してください](automation-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="54f82-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="54f82-129">[メンバー **] セクション** で、1 つ以上の条件を使用してデバイスを識別して含める。</span><span class="sxs-lookup"><span data-stu-id="54f82-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="54f82-130">[ユーザー **アクセス] タブ** で、作成するデバイス グループにアクセスできる [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="54f82-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="54f82-131">デバイス **グループの** 設定が完了したら、[完了] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54f82-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="54f82-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="54f82-132">Next steps</span></span>

- [<span data-ttu-id="54f82-133">アクション センターにアクセスして、保留中の修復アクションと完了済み修復アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="54f82-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="54f82-134">保留中のアクションの確認と承認</span><span class="sxs-lookup"><span data-stu-id="54f82-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="54f82-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="54f82-135">See also</span></span>

- [<span data-ttu-id="54f82-136">エンドポイント向け Microsoft Defender で誤検知/負に対処する</span><span class="sxs-lookup"><span data-stu-id="54f82-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)