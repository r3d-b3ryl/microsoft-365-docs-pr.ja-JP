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
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841348"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fa3f2-104">Microsoft Defender for Endpoint で自動調査および修復機能を構成する</span><span class="sxs-lookup"><span data-stu-id="fa3f2-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fa3f2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fa3f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="fa3f2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fa3f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fa3f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa3f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fa3f2-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fa3f2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fa3f2-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fa3f2-110">組織が[](/microsoft-365/security/defender-endpoint/automated-investigations)Microsoft [Defender for Endpoint (Defender for Endpoint)](/windows/security/threat-protection/)を使用している場合、自動調査および修復機能により、セキュリティ運用チームの時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="fa3f2-111">このブログ記事で [説明するように、](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)これらの機能は、セキュリティ アナリストが脅威の調査と修復に必要な理想的な手順を模倣します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="fa3f2-112">[自動調査と修復の詳細については、次のリンクを参照してください](/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="fa3f2-113">自動調査と修復を構成するには、</span><span class="sxs-lookup"><span data-stu-id="fa3f2-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="fa3f2-114">[機能を有効にする](#turn-on-automated-investigation-and-remediation)。そして</span><span class="sxs-lookup"><span data-stu-id="fa3f2-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="fa3f2-115">[デバイス グループを設定します](#set-up-device-groups)。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="fa3f2-116">自動調査と修復を有効にする</span><span class="sxs-lookup"><span data-stu-id="fa3f2-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="fa3f2-117">グローバル管理者またはセキュリティ管理者として、管理者 ( ) にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="fa3f2-118">ナビゲーション ウィンドウで、[次へ]**を設定。**</span><span class="sxs-lookup"><span data-stu-id="fa3f2-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="fa3f2-119">[全般] **セクションで** 、[高度な機能 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="fa3f2-120">[自動調査]**と [アラートの\*\*\*\*自動解決] の両方をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="fa3f2-121">デバイス グループを設定する</span><span class="sxs-lookup"><span data-stu-id="fa3f2-121">Set up device groups</span></span>

1. <span data-ttu-id="fa3f2-122">[Microsoft Defender セキュリティ センター ] ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) の [アクセス許可]**設定** で、[デバイス グループ]**を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="fa3f2-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="fa3f2-123">[+ **デバイス グループの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="fa3f2-124">次のように、少なくとも 1 つのデバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="fa3f2-125">デバイス グループの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="fa3f2-126">[オートメーション レベル **] ボックスの** 一覧で、[完全] などのレベルを選択し、脅威 **を自動的に修復します**。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="fa3f2-127">オートメーション レベルは、修復アクションが自動的に実行されるのか、承認時にのみ実行されるのかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="fa3f2-128">詳細については、「自動調査と [修復」の「オートメーション レベル」を参照してください](automation-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="fa3f2-129">[メンバー **] セクション** で、1 つ以上の条件を使用してデバイスを識別して含める。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="fa3f2-130">[ユーザー **アクセス] タブ** で [](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context)、Azure Active Directoryするデバイス グループにアクセスする必要があるグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="fa3f2-131">デバイス **グループの** 設定が完了したら、[完了] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa3f2-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa3f2-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="fa3f2-132">Next steps</span></span>

- [<span data-ttu-id="fa3f2-133">アクション センターにアクセスして、保留中の修復アクションと完了済み修復アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="fa3f2-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="fa3f2-134">保留中のアクションの確認と承認</span><span class="sxs-lookup"><span data-stu-id="fa3f2-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="fa3f2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa3f2-135">See also</span></span>

- [<span data-ttu-id="fa3f2-136">Microsoft Defender for Endpoint での誤検出/検出漏れに対処する</span><span class="sxs-lookup"><span data-stu-id="fa3f2-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
