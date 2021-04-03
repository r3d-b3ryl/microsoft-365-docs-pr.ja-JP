---
title: Microsoft Threat Protection で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索クエリ結果の脅威と影響を受けるアセットにすばやく対処する
keywords: 高度な狩猟、脅威狩り、サイバー脅威の狩猟、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、回避タイムアウト、コマンド ライン、プロセス ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500533"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="db8ac-104">高度な検索クエリの結果に対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="db8ac-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="db8ac-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="db8ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="db8ac-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db8ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="db8ac-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="db8ac-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db8ac-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="db8ac-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="db8ac-109">強力で包括的なアクション オプションを使用して、高度な狩[](advanced-hunting-overview.md)猟で見つけた脅威を迅速に含め、または侵害された資産に対処できます。</span><span class="sxs-lookup"><span data-stu-id="db8ac-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="db8ac-110">これらのオプションを使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db8ac-110">With these options, you can:</span></span>

- <span data-ttu-id="db8ac-111">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="db8ac-111">Take various actions on devices</span></span>
- <span data-ttu-id="db8ac-112">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="db8ac-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="db8ac-113">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="db8ac-113">Required permissions</span></span>

<span data-ttu-id="db8ac-114">高度な検索を通じてアクションを実行するには、デバイスに修復アクションを送信するためのアクセス許可を持つ Defender for Endpoint の役割 [が必要です](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="db8ac-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="db8ac-115">アクションを実行できない場合は、次のアクセス許可を取得する方法について、グローバル管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="db8ac-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="db8ac-116">*脅威と脆弱性管理>アクティブな修復アクション - 修復処理*</span><span class="sxs-lookup"><span data-stu-id="db8ac-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="db8ac-117">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="db8ac-117">Take various actions on devices</span></span>

<span data-ttu-id="db8ac-118">クエリ結果の列で識別されるデバイスに対して、次 `DeviceId` のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="db8ac-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="db8ac-119">影響を受けるデバイスを分離して、感染を含むか、攻撃が横方向に移動しなかっ</span><span class="sxs-lookup"><span data-stu-id="db8ac-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="db8ac-120">調査パッケージを収集して、より多くの調査情報を取得する</span><span class="sxs-lookup"><span data-stu-id="db8ac-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="db8ac-121">ウイルス対策スキャンを実行して、最新のセキュリティ インテリジェンス更新プログラムを使用して脅威を検索および削除する</span><span class="sxs-lookup"><span data-stu-id="db8ac-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="db8ac-122">自動調査を開始して、デバイスおよび他の影響を受ける可能性のあるデバイス上の脅威を確認および修復する</span><span class="sxs-lookup"><span data-stu-id="db8ac-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="db8ac-123">アプリの実行を Microsoft が署名した実行可能ファイルにのみ制限し、マルウェアや他の信頼されていない実行可能ファイルによる後続の脅威アクティビティを防止する</span><span class="sxs-lookup"><span data-stu-id="db8ac-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="db8ac-124">Defender for Endpoint を通じてこれらの応答アクションがどのように実行されるのかについて詳しくは、デバイス [での応答アクションに関するページをご覧ください](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="db8ac-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="db8ac-125">検疫ファイル</span><span class="sxs-lookup"><span data-stu-id="db8ac-125">Quarantine files</span></span>

<span data-ttu-id="db8ac-126">ファイルに検疫アクション *を* 展開すると、ファイルが検出された場合に自動的に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="db8ac-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="db8ac-127">このアクションを選択すると、次の列から選択して、検疫するクエリ結果内のファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="db8ac-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="db8ac-128">`SHA1` — 最も高度な検索テーブルでは、記録されたアクションの影響を受けたファイルの SHA-1 です。</span><span class="sxs-lookup"><span data-stu-id="db8ac-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="db8ac-129">たとえば、ファイルがコピーされた場合、これはコピーされたファイルです。</span><span class="sxs-lookup"><span data-stu-id="db8ac-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="db8ac-130">`InitiatingProcessSHA1` — 最も高度な検索テーブルでは、記録されたアクションの開始を担当するファイルです。</span><span class="sxs-lookup"><span data-stu-id="db8ac-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="db8ac-131">たとえば、子プロセスが起動された場合、これは親プロセスになります。</span><span class="sxs-lookup"><span data-stu-id="db8ac-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="db8ac-132">`SHA256` — これは、列で識別されるファイルに相当する SHA-256 `SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="db8ac-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="db8ac-133">`InitiatingProcessSHA256` — これは、列で識別されるファイルに相当する SHA-256 `InitiatingProcessSHA1` です。</span><span class="sxs-lookup"><span data-stu-id="db8ac-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="db8ac-134">検疫アクションの実行方法とファイルの復元方法の詳細については、「ファイルに対する応答アクション」 [を参照してください](respond-file-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="db8ac-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="db8ac-135">ファイルを検索して検疫するには、クエリ結果に値を `DeviceId` デバイス識別子として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="db8ac-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="db8ac-136">アクションを行う</span><span class="sxs-lookup"><span data-stu-id="db8ac-136">Take action</span></span>

<span data-ttu-id="db8ac-137">説明されているアクションのいずれかを実行するには、クエリ結果で 1 つ以上のレコードを選択し、[アクションの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="db8ac-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="db8ac-138">ウィザードを使用すると、優先するアクションを選択して送信するプロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="db8ac-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![選択したレコードの画像(レコードを検査するパネル付き)](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="db8ac-140">実行されたアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="db8ac-140">Review actions taken</span></span>

<span data-ttu-id="db8ac-141">各アクションは、アクション センターの [アクション センターの履歴 ] ( [ security.microsoft.com/action-center/history ] の下に  >  [個別に記録されます](https://security.microsoft.com/action-center/history)。</span><span class="sxs-lookup"><span data-stu-id="db8ac-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="db8ac-142">アクション センターに移動して、各アクションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="db8ac-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="db8ac-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="db8ac-143">Related topics</span></span>

- [<span data-ttu-id="db8ac-144">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="db8ac-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="db8ac-145">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="db8ac-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="db8ac-146">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="db8ac-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="db8ac-147">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="db8ac-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="db8ac-148">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="db8ac-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="db8ac-149">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="db8ac-149">Custom detections overview</span></span>](overview-custom-detections.md)
