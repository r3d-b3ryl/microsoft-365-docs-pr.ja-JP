---
title: Microsoft 365 Defender で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索クエリ結果の脅威と影響を受けるアセットにすばやく対処する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、アクションの実行
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0c088375cd784b411fdce417d77b1ea176bcee26
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932907"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="75c40-104">高度な検索クエリの結果に対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="75c40-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75c40-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="75c40-105">**Applies to:**</span></span>
- <span data-ttu-id="75c40-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75c40-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="75c40-107">強力で包括的なアクション オプションを使用して、高度な狩[](advanced-hunting-overview.md)猟で見つけた脅威を迅速に含め、または侵害された資産に対処できます。</span><span class="sxs-lookup"><span data-stu-id="75c40-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="75c40-108">これらのオプションを使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="75c40-108">With these options, you can:</span></span>

- <span data-ttu-id="75c40-109">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="75c40-109">Take various actions on devices</span></span>
- <span data-ttu-id="75c40-110">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="75c40-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="75c40-111">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="75c40-111">Required permissions</span></span>
<span data-ttu-id="75c40-112">高度な検索を通じてアクションを実行するには、デバイスに修復アクションを送信するためのアクセス許可を持つ Microsoft Defender for Endpoint の役割 [が必要です](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="75c40-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="75c40-113">アクションを実行できない場合は、次のアクセス許可を取得する方法について、グローバル管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="75c40-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="75c40-114">*脅威と脆弱性管理>アクティブな修復アクション - 修復処理*</span><span class="sxs-lookup"><span data-stu-id="75c40-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="75c40-115">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="75c40-115">Take various actions on devices</span></span>
<span data-ttu-id="75c40-116">クエリ結果の列で識別されるデバイスに対して、次 `DeviceId` のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="75c40-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="75c40-117">影響を受けるデバイスを分離して、感染を含むか、攻撃が横方向に移動しなかっ</span><span class="sxs-lookup"><span data-stu-id="75c40-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="75c40-118">調査パッケージを収集して、より多くの調査情報を取得する</span><span class="sxs-lookup"><span data-stu-id="75c40-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="75c40-119">ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を検索および削除する</span><span class="sxs-lookup"><span data-stu-id="75c40-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="75c40-120">自動調査を開始して、デバイスおよび他の影響を受ける可能性のあるデバイス上の脅威を確認および修復する</span><span class="sxs-lookup"><span data-stu-id="75c40-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="75c40-121">アプリの実行を Microsoft が署名した実行可能ファイルにのみ制限し、マルウェアや他の信頼されていない実行可能ファイルによる後続の脅威アクティビティを防止する</span><span class="sxs-lookup"><span data-stu-id="75c40-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="75c40-122">これらの応答アクションが Microsoft Defender for Endpoint を介して実行される方法の詳細については、「デバイスでの応答 [アクション」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="75c40-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="75c40-123">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="75c40-123">Quarantine files</span></span>
<span data-ttu-id="75c40-124">ファイルに検疫アクション *を* 展開すると、ファイルが検出された場合に自動的に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="75c40-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="75c40-125">このアクションを選択すると、次の列から選択して、検疫するクエリ結果内のファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="75c40-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="75c40-126">`SHA1` — 最も高度な検索テーブルでは、記録されたアクションの影響を受けたファイルの SHA-1 です。</span><span class="sxs-lookup"><span data-stu-id="75c40-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="75c40-127">たとえば、ファイルがコピーされた場合、これはコピーされたファイルです。</span><span class="sxs-lookup"><span data-stu-id="75c40-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="75c40-128">`InitiatingProcessSHA1` — 最も高度な検索テーブルでは、記録されたアクションの開始を担当するファイルです。</span><span class="sxs-lookup"><span data-stu-id="75c40-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="75c40-129">たとえば、子プロセスが起動された場合、これは親プロセスになります。</span><span class="sxs-lookup"><span data-stu-id="75c40-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="75c40-130">`SHA256` — これは、列で識別されるファイルに相当する SHA-256 `SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="75c40-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="75c40-131">`InitiatingProcessSHA256` — これは、列で識別されるファイルに相当する SHA-256 `InitiatingProcessSHA1` です。</span><span class="sxs-lookup"><span data-stu-id="75c40-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="75c40-132">検疫アクションの実行方法とファイルの復元方法の詳細については、「ファイルに対する応答アクション」 [を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。</span><span class="sxs-lookup"><span data-stu-id="75c40-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="75c40-133">ファイルを検索して検疫するには、クエリ結果に値を `DeviceId` デバイス識別子として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="75c40-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="75c40-134">アクションを行う</span><span class="sxs-lookup"><span data-stu-id="75c40-134">Take action</span></span>
<span data-ttu-id="75c40-135">説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[アクションの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="75c40-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="75c40-136">ウィザードを使用すると、優先するアクションを選択して送信するプロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="75c40-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![選択したレコードの画像(レコードを検査するパネル付き)](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="75c40-138">実行されたアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="75c40-138">Review actions taken</span></span>
<span data-ttu-id="75c40-139">各アクションは、アクション センターの[](m365d-action-center.md)[履歴] ([アクション センター履歴] ( [ security.microsoft.com/action-center/history] の下のアクション センター  >  [に個別に記録されます](https://security.microsoft.com/action-center/history)。</span><span class="sxs-lookup"><span data-stu-id="75c40-139">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="75c40-140">アクション センターに移動して、各アクションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="75c40-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="75c40-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="75c40-141">Related topics</span></span>
- [<span data-ttu-id="75c40-142">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="75c40-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75c40-143">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="75c40-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="75c40-144">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="75c40-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="75c40-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="75c40-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="75c40-146">アクション センターの概要</span><span class="sxs-lookup"><span data-stu-id="75c40-146">Action center overview</span></span>](m365d-action-center.md)
