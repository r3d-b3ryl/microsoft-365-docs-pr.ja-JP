---
title: Defender で高度な検索クエリの結果に対してMicrosoft 365する
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
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952610"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="786b8-104">高度な検索クエリの結果に対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="786b8-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="786b8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="786b8-105">**Applies to:**</span></span>
- <span data-ttu-id="786b8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="786b8-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="786b8-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="786b8-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="786b8-108">強力で包括的なアクション オプションを使用して、高度な狩[](advanced-hunting-overview.md)猟で見つけた脅威を迅速に含め、または侵害された資産に対処できます。</span><span class="sxs-lookup"><span data-stu-id="786b8-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="786b8-109">これらのオプションを使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="786b8-109">With these options, you can:</span></span>

- <span data-ttu-id="786b8-110">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="786b8-110">Take various actions on devices</span></span>
- <span data-ttu-id="786b8-111">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="786b8-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="786b8-112">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="786b8-112">Required permissions</span></span>
<span data-ttu-id="786b8-113">高度な検索を通じてアクションを実行するには、デバイスに修復アクションを送信するためのアクセス許可を持つ Microsoft Defender for Endpoint の役割 [が必要です](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="786b8-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="786b8-114">アクションを実行できない場合は、次のアクセス許可を取得する方法について、グローバル管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="786b8-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="786b8-115">*脅威と脅威に対>アクティブな脆弱性の管理アクション - 修復処理*</span><span class="sxs-lookup"><span data-stu-id="786b8-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="786b8-116">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="786b8-116">Take various actions on devices</span></span>
<span data-ttu-id="786b8-117">クエリ結果の列で識別されるデバイスに対して、次 `DeviceId` のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="786b8-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="786b8-118">影響を受けるデバイスを分離して、感染を含むか、攻撃が横方向に移動しなかっ</span><span class="sxs-lookup"><span data-stu-id="786b8-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="786b8-119">調査パッケージを収集して、より多くの調査情報を取得する</span><span class="sxs-lookup"><span data-stu-id="786b8-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="786b8-120">ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を検索および削除する</span><span class="sxs-lookup"><span data-stu-id="786b8-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="786b8-121">自動調査を開始して、デバイスおよび他の影響を受ける可能性のあるデバイス上の脅威を確認および修復する</span><span class="sxs-lookup"><span data-stu-id="786b8-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="786b8-122">アプリの実行を Microsoft が署名した実行可能ファイルにのみ制限し、マルウェアや他の信頼されていない実行可能ファイルによる後続の脅威アクティビティを防止する</span><span class="sxs-lookup"><span data-stu-id="786b8-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="786b8-123">これらの応答アクションが Microsoft Defender for Endpoint を介して実行される方法の詳細については、「デバイスでの応答 [アクション」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="786b8-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="786b8-124">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="786b8-124">Quarantine files</span></span>
<span data-ttu-id="786b8-125">ファイルに検疫アクション *を* 展開すると、ファイルが検出された場合に自動的に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="786b8-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="786b8-126">このアクションを選択すると、次の列から選択して、検疫するクエリ結果内のファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="786b8-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="786b8-127">`SHA1` — 最も高度な検索テーブルでは、記録されたアクションの影響を受けたファイルの SHA-1 です。</span><span class="sxs-lookup"><span data-stu-id="786b8-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="786b8-128">たとえば、ファイルがコピーされた場合、これはコピーされたファイルです。</span><span class="sxs-lookup"><span data-stu-id="786b8-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="786b8-129">`InitiatingProcessSHA1` — 最も高度な検索テーブルでは、記録されたアクションの開始を担当するファイルです。</span><span class="sxs-lookup"><span data-stu-id="786b8-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="786b8-130">たとえば、子プロセスが起動された場合、これは親プロセスになります。</span><span class="sxs-lookup"><span data-stu-id="786b8-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="786b8-131">`SHA256` — これは、列で識別されるファイルに相当する SHA-256 `SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="786b8-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="786b8-132">`InitiatingProcessSHA256` — これは、列で識別されるファイルに相当する SHA-256 `InitiatingProcessSHA1` です。</span><span class="sxs-lookup"><span data-stu-id="786b8-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="786b8-133">検疫アクションの実行方法とファイルの復元方法の詳細については、「ファイルに対する応答アクション」 [を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。</span><span class="sxs-lookup"><span data-stu-id="786b8-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="786b8-134">ファイルを検索して検疫するには、クエリ結果に値を `DeviceId` デバイス識別子として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="786b8-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="786b8-135">アクションを行う</span><span class="sxs-lookup"><span data-stu-id="786b8-135">Take action</span></span>
<span data-ttu-id="786b8-136">説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[アクションの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="786b8-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="786b8-137">ウィザードを使用すると、優先するアクションを選択して送信するプロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="786b8-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![選択したレコードの画像(レコードを検査するパネル付き)](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="786b8-139">実行されたアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="786b8-139">Review actions taken</span></span>
<span data-ttu-id="786b8-140">各アクションは、アクション センターの[](m365d-action-center.md)[履歴] ([アクション センター履歴] ( [ security.microsoft.com/action-center/history] の下のアクション センター  >  [に個別に記録されます](https://security.microsoft.com/action-center/history)。</span><span class="sxs-lookup"><span data-stu-id="786b8-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="786b8-141">アクション センターに移動して、各アクションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="786b8-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="786b8-142">この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="786b8-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="786b8-143">[Defender を有効Microsoft 365、](m365d-enable.md)より多くのデータ ソースを使用して脅威を探します。</span><span class="sxs-lookup"><span data-stu-id="786b8-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="786b8-144">「Advanced Hunting queries from Microsoft Defender for Endpoint 」 の手順に従って、高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に[移動できます](advanced-hunting-migrate-from-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="786b8-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="786b8-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="786b8-145">Related topics</span></span>
- [<span data-ttu-id="786b8-146">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="786b8-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="786b8-147">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="786b8-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="786b8-148">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="786b8-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="786b8-149">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="786b8-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="786b8-150">アクション センターの概要</span><span class="sxs-lookup"><span data-stu-id="786b8-150">Action center overview</span></span>](m365d-action-center.md)
